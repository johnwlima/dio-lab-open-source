# Scripts API Documentation

<div align="center">
  <img src="https://img.shields.io/badge/Scripts-API-FFA500?style=for-the-badge&logo=python&logoColor=white" alt="Scripts API">
  <h1>Automation Scripts API</h1>
  <p>Automated workflows and repository management tools</p>
</div>

## Overview

The Scripts API provides automation tools for repository management, workflow triggering, and bulk operations on GitHub repositories. The main component is the PR Labeler script for automated pull request management.

**Source:** [`scripts/PR_Labeler_DIO_Lab_Workflow_Trigger.ipynb`](../scripts/PR_Labeler_DIO_Lab_Workflow_Trigger.ipynb)  
**Environment:** Jupyter Notebook / Google Colab  
**Language:** Python 3.7+  
**Dependencies:** `requests`, `time`

## Quick Start

```python
# Import required modules
import requests
import time

# Configure GitHub settings
GITHUB_TOKEN = 'your_personal_access_token'
OWNER = 'your_github_username'
REPO = 'your_repository_name'

# Run PR labeling workflow
python PR_Labeler_DIO_Lab_Workflow_Trigger.ipynb
```

## PR Labeler Script API

### Classes

#### 1. GitHubConfig

Configuration class for GitHub API access and authentication.

```python
class GitHubConfig:
    """Configurações relacionadas ao GitHub e ao repositório."""
    TOKEN = 'ghp_your_personal_access_token'
    OWNER = 'digitalinnovationone'
    REPO = 'dio-lab-open-source'
    HEADERS = {
        'Authorization': f'token {TOKEN}',
        'Accept': 'application/vnd.github.v3+json'
    }
```

**Attributes:**

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `TOKEN` | string | GitHub Personal Access Token | `'ghp_xxxxxxxxxxxx'` |
| `OWNER` | string | Repository owner username | `'digitalinnovationone'` |
| `REPO` | string | Repository name | `'dio-lab-open-source'` |
| `HEADERS` | dict | HTTP headers for API requests | GitHub API v3 headers |

**Security Note:** The token in the source code has been revoked by GitHub for security purposes.

#### 2. ScriptConfig

Configuration class for script-specific settings and behavior.

```python
class ScriptConfig:
    """Configurações específicas do script."""
    DIO_LAB_WORKFLOW_TRIGGER_LABEL = 'run dio workflow'
    DELAY_SECONDS = 10
```

**Attributes:**

| Attribute | Type | Description | Default |
|-----------|------|-------------|---------|
| `DIO_LAB_WORKFLOW_TRIGGER_LABEL` | string | Label to apply to PRs | `'run dio workflow'` |
| `DELAY_SECONDS` | int | Delay between API calls | `10` |

### Functions

#### 1. obter_prs_abertos()

Retrieves all open pull requests from the configured repository.

```python
def obter_prs_abertos():
    """Retorna uma lista de todos os PRs abertos."""
    next_page = 1
    all_prs = []

    while True:
        try:
            response = requests.get(
                f'https://api.github.com/repos/{GitHubConfig.OWNER}/{GitHubConfig.REPO}/pulls?page={next_page}&per_page=100', 
                headers=GitHubConfig.HEADERS
            )
            response.raise_for_status()
        except requests.RequestException as e:
            print(f"Erro ao recuperar PRs: {e}")
            return []

        prs = response.json()
        all_prs.extend(prs)

        if len(prs) < 100:
            break

        next_page += 1

    print(f"Recuperados {len(all_prs)} PRs abertos no total.")
    return all_prs
```

**Returns:**
- `list`: List of pull request objects from GitHub API

**Raises:**
- `requests.RequestException`: If API request fails

**Features:**
- Handles pagination automatically
- Fetches 100 PRs per page (GitHub API maximum)
- Comprehensive error handling
- Progress reporting

**Usage Example:**
```python
prs = obter_prs_abertos()
print(f"Found {len(prs)} open pull requests")

for pr in prs:
    print(f"PR #{pr['number']}: {pr['title']}")
```

#### 2. adicionar_label(pr_number)

Adds the configured label to a specific pull request.

```python
def adicionar_label(pr_number):
    """Adiciona a label ao PR especificado."""
    label_data = {'labels': [ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL]}
    try:
        response = requests.post(
            f'https://api.github.com/repos/{GitHubConfig.OWNER}/{GitHubConfig.REPO}/issues/{pr_number}/labels', 
            headers=GitHubConfig.HEADERS, 
            json=label_data
        )
        response.raise_for_status()
    except requests.RequestException as e:
        print(f"Erro ao adicionar label ao PR {pr_number}: {e}")
        return None

    return response.status_code
```

**Parameters:**
- `pr_number` (int): Pull request number to label

**Returns:**
- `int`: HTTP status code (200 for success)
- `None`: If request failed

**Raises:**
- `requests.RequestException`: If API request fails

**Usage Example:**
```python
# Add label to PR #123
status = adicionar_label(123)
if status == 200:
    print("Label added successfully")
else:
    print("Failed to add label")
```

#### 3. main()

Main execution function that orchestrates the labeling workflow.

```python
def main():
    prs_abertos = obter_prs_abertos()
    prs_abertos.reverse()

    for pr in prs_abertos:
        pr_number = pr['number']
        labels = [label['name'] for label in pr['labels']]

        if ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL not in labels:
            status_code = adicionar_label(pr_number)
            if status_code:
                print(f"Adicionado label ao PR #{pr_number}, Resposta: {status_code}")
            time.sleep(ScriptConfig.DELAY_SECONDS)
        else:
            print(f"PR #{pr_number} já possui o label. Pulando.")
```

**Features:**
- Processes PRs in reverse order (oldest first)
- Skips PRs that already have the label
- Implements rate limiting with configurable delay
- Comprehensive logging of actions

**Workflow:**
1. Fetch all open pull requests
2. Reverse order to process oldest first
3. Check if PR already has target label
4. Add label if missing
5. Sleep between requests to avoid rate limiting
6. Log all actions and results

## API Usage Examples

### Basic Usage

```python
# Simple script execution
if __name__ == "__main__":
    main()
```

### Custom Configuration

```python
# Custom configuration
class CustomConfig:
    TOKEN = 'your_token_here'
    OWNER = 'your_username'
    REPO = 'your_repository'
    LABEL = 'custom-workflow-trigger'
    DELAY = 5

# Override default configuration
GitHubConfig.TOKEN = CustomConfig.TOKEN
GitHubConfig.OWNER = CustomConfig.OWNER
GitHubConfig.REPO = CustomConfig.REPO
ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL = CustomConfig.LABEL
ScriptConfig.DELAY_SECONDS = CustomConfig.DELAY
```

### Selective Processing

```python
def process_specific_prs(pr_numbers):
    """Process only specific PR numbers."""
    for pr_number in pr_numbers:
        status = adicionar_label(pr_number)
        if status == 200:
            print(f"Successfully labeled PR #{pr_number}")
        time.sleep(ScriptConfig.DELAY_SECONDS)

# Usage
priority_prs = [123, 456, 789]
process_specific_prs(priority_prs)
```

### Batch Label Management

```python
def remove_label_from_pr(pr_number, label_name):
    """Remove specific label from PR."""
    try:
        response = requests.delete(
            f'https://api.github.com/repos/{GitHubConfig.OWNER}/{GitHubConfig.REPO}/issues/{pr_number}/labels/{label_name}',
            headers=GitHubConfig.HEADERS
        )
        response.raise_for_status()
        return response.status_code
    except requests.RequestException as e:
        print(f"Error removing label from PR {pr_number}: {e}")
        return None

def bulk_label_operations(operation='add'):
    """Perform bulk label operations."""
    prs = obter_prs_abertos()
    
    for pr in prs:
        pr_number = pr['number']
        labels = [label['name'] for label in pr['labels']]
        target_label = ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL
        
        if operation == 'add' and target_label not in labels:
            status = adicionar_label(pr_number)
            print(f"Added label to PR #{pr_number}: {status}")
        elif operation == 'remove' and target_label in labels:
            status = remove_label_from_pr(pr_number, target_label)
            print(f"Removed label from PR #{pr_number}: {status}")
        
        time.sleep(ScriptConfig.DELAY_SECONDS)
```

### Analytics and Reporting

```python
def analyze_pr_labels():
    """Analyze label distribution across PRs."""
    prs = obter_prs_abertos()
    label_stats = {}
    
    for pr in prs:
        for label in pr['labels']:
            label_name = label['name']
            label_stats[label_name] = label_stats.get(label_name, 0) + 1
    
    print("Label Distribution:")
    for label, count in sorted(label_stats.items(), key=lambda x: x[1], reverse=True):
        print(f"  {label}: {count} PRs")
    
    return label_stats

def generate_pr_report():
    """Generate comprehensive PR report."""
    prs = obter_prs_abertos()
    target_label = ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL
    
    labeled_prs = 0
    unlabeled_prs = 0
    
    for pr in prs:
        labels = [label['name'] for label in pr['labels']]
        if target_label in labels:
            labeled_prs += 1
        else:
            unlabeled_prs += 1
    
    print(f"PR Report:")
    print(f"  Total open PRs: {len(prs)}")
    print(f"  PRs with '{target_label}' label: {labeled_prs}")
    print(f"  PRs without '{target_label}' label: {unlabeled_prs}")
    print(f"  Coverage: {(labeled_prs/len(prs)*100):.1f}%")
```

## Configuration Management

### Environment Variables

```python
import os

# Use environment variables for sensitive data
class EnvironmentConfig:
    TOKEN = os.getenv('GITHUB_TOKEN')
    OWNER = os.getenv('GITHUB_OWNER', 'digitalinnovationone')
    REPO = os.getenv('GITHUB_REPO', 'dio-lab-open-source')
    LABEL = os.getenv('WORKFLOW_LABEL', 'run dio workflow')
    DELAY = int(os.getenv('API_DELAY', '10'))

# Validate configuration
def validate_config():
    """Validate that all required configuration is present."""
    if not EnvironmentConfig.TOKEN:
        raise ValueError("GITHUB_TOKEN environment variable is required")
    if not EnvironmentConfig.OWNER:
        raise ValueError("GITHUB_OWNER environment variable is required")
    if not EnvironmentConfig.REPO:
        raise ValueError("GITHUB_REPO environment variable is required")
    
    print("Configuration validated successfully")
```

### Configuration File

```python
import json

def load_config_from_file(config_path='config.json'):
    """Load configuration from JSON file."""
    try:
        with open(config_path, 'r') as f:
            config = json.load(f)
        
        GitHubConfig.TOKEN = config['github']['token']
        GitHubConfig.OWNER = config['github']['owner']
        GitHubConfig.REPO = config['github']['repo']
        ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL = config['script']['label']
        ScriptConfig.DELAY_SECONDS = config['script']['delay']
        
        print(f"Configuration loaded from {config_path}")
    except FileNotFoundError:
        print(f"Configuration file {config_path} not found, using defaults")
    except json.JSONDecodeError as e:
        print(f"Error parsing configuration file: {e}")

# Example config.json
"""
{
  "github": {
    "token": "ghp_your_token_here",
    "owner": "your_username",
    "repo": "your_repository"
  },
  "script": {
    "label": "run dio workflow",
    "delay": 10
  }
}
"""
```

## Error Handling and Logging

### Enhanced Error Handling

```python
import logging
from datetime import datetime

# Configure logging
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('pr_labeler.log'),
        logging.StreamHandler()
    ]
)

def safe_api_request(url, method='GET', **kwargs):
    """Make API request with comprehensive error handling."""
    max_retries = 3
    retry_delay = 5
    
    for attempt in range(max_retries):
        try:
            if method == 'GET':
                response = requests.get(url, **kwargs)
            elif method == 'POST':
                response = requests.post(url, **kwargs)
            elif method == 'DELETE':
                response = requests.delete(url, **kwargs)
            else:
                raise ValueError(f"Unsupported HTTP method: {method}")
            
            response.raise_for_status()
            return response
            
        except requests.exceptions.Timeout:
            logging.warning(f"Request timeout, attempt {attempt + 1}/{max_retries}")
        except requests.exceptions.ConnectionError:
            logging.warning(f"Connection error, attempt {attempt + 1}/{max_retries}")
        except requests.exceptions.HTTPError as e:
            if response.status_code == 403:
                logging.error("Rate limit exceeded, waiting...")
                time.sleep(60)  # Wait 1 minute for rate limit reset
            elif response.status_code == 401:
                logging.error("Authentication failed, check token")
                break
            else:
                logging.error(f"HTTP error {response.status_code}: {e}")
        except requests.exceptions.RequestException as e:
            logging.error(f"Request failed: {e}")
        
        if attempt < max_retries - 1:
            time.sleep(retry_delay)
    
    logging.error(f"Failed to complete request after {max_retries} attempts")
    return None
```

### Progress Tracking

```python
def main_with_progress():
    """Main function with progress tracking."""
    start_time = datetime.now()
    logging.info("Starting PR labeling workflow")
    
    try:
        prs = obter_prs_abertos()
        total_prs = len(prs)
        processed = 0
        labeled = 0
        skipped = 0
        
        for i, pr in enumerate(prs, 1):
            pr_number = pr['number']
            labels = [label['name'] for label in pr['labels']]
            
            # Progress indicator
            progress = (i / total_prs) * 100
            print(f"Progress: {progress:.1f}% ({i}/{total_prs})")
            
            if ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL not in labels:
                status_code = adicionar_label(pr_number)
                if status_code == 200:
                    labeled += 1
                    logging.info(f"Labeled PR #{pr_number}")
                time.sleep(ScriptConfig.DELAY_SECONDS)
            else:
                skipped += 1
                logging.info(f"Skipped PR #{pr_number} (already labeled)")
            
            processed += 1
        
        # Summary
        end_time = datetime.now()
        duration = end_time - start_time
        
        logging.info("Workflow completed")
        logging.info(f"Duration: {duration}")
        logging.info(f"Total PRs processed: {processed}")
        logging.info(f"PRs labeled: {labeled}")
        logging.info(f"PRs skipped: {skipped}")
        
    except Exception as e:
        logging.error(f"Workflow failed: {e}")
        raise
```

## Advanced Features

### Conditional Labeling

```python
def conditional_labeling():
    """Apply labels based on PR criteria."""
    prs = obter_prs_abertos()
    
    for pr in prs:
        pr_number = pr['number']
        title = pr['title'].lower()
        body = pr['body'].lower() if pr['body'] else ''
        author = pr['user']['login']
        
        # Define labeling rules
        labels_to_add = []
        
        # Feature detection
        if 'feat' in title or 'feature' in title:
            labels_to_add.append('feature')
        
        # Bug fix detection
        if 'fix' in title or 'bug' in title:
            labels_to_add.append('bug')
        
        # Documentation detection
        if 'doc' in title or 'readme' in title:
            labels_to_add.append('documentation')
        
        # Priority detection
        if 'urgent' in title or 'critical' in title:
            labels_to_add.append('priority-high')
        
        # Apply labels
        for label in labels_to_add:
            add_specific_label(pr_number, label)
            time.sleep(1)  # Brief delay between label additions

def add_specific_label(pr_number, label_name):
    """Add a specific label to a PR."""
    label_data = {'labels': [label_name]}
    try:
        response = requests.post(
            f'https://api.github.com/repos/{GitHubConfig.OWNER}/{GitHubConfig.REPO}/issues/{pr_number}/labels',
            headers=GitHubConfig.HEADERS,
            json=label_data
        )
        response.raise_for_status()
        return response.status_code
    except requests.RequestException as e:
        logging.error(f"Failed to add label '{label_name}' to PR {pr_number}: {e}")
        return None
```

### Webhook Integration

```python
from flask import Flask, request, jsonify
import hmac
import hashlib

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def github_webhook():
    """Handle GitHub webhook events."""
    # Verify webhook signature
    signature = request.headers.get('X-Hub-Signature-256')
    if not verify_signature(request.data, signature):
        return jsonify({'error': 'Invalid signature'}), 401
    
    event_type = request.headers.get('X-GitHub-Event')
    payload = request.json
    
    if event_type == 'pull_request':
        handle_pr_event(payload)
    elif event_type == 'issues':
        handle_issue_event(payload)
    
    return jsonify({'status': 'success'}), 200

def verify_signature(payload_body, signature_header):
    """Verify webhook signature."""
    if not signature_header:
        return False
    
    expected_signature = hmac.new(
        WEBHOOK_SECRET.encode('utf-8'),
        payload_body,
        hashlib.sha256
    ).hexdigest()
    
    return hmac.compare_digest(
        f"sha256={expected_signature}",
        signature_header
    )

def handle_pr_event(payload):
    """Handle pull request events."""
    action = payload['action']
    pr_number = payload['number']
    
    if action == 'opened':
        # Auto-label new PRs
        adicionar_label(pr_number)
        logging.info(f"Auto-labeled new PR #{pr_number}")
    elif action == 'closed':
        # Remove workflow labels from closed PRs
        remove_label_from_pr(pr_number, ScriptConfig.DIO_LAB_WORKFLOW_TRIGGER_LABEL)
        logging.info(f"Removed workflow label from closed PR #{pr_number}")
```

## Deployment Options

### Google Colab Deployment

```python
# Install dependencies in Colab
!pip install requests

# Mount Google Drive for persistent configuration
from google.colab import drive
drive.mount('/content/drive')

# Load configuration from Drive
import sys
sys.path.append('/content/drive/My Drive/github-automation')

# Run the script
exec(open('/content/drive/My Drive/github-automation/pr_labeler.py').read())
```

### GitHub Actions Integration

```yaml
# .github/workflows/pr-labeler.yml
name: PR Labeler

on:
  schedule:
    - cron: '0 */6 * * *'  # Run every 6 hours
  workflow_dispatch:

jobs:
  label-prs:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'
      
      - name: Install dependencies
        run: |
          pip install requests
      
      - name: Run PR Labeler
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          GITHUB_OWNER: ${{ github.repository_owner }}
          GITHUB_REPO: ${{ github.event.repository.name }}
        run: |
          python scripts/pr_labeler.py
```

### Docker Deployment

```dockerfile
# Dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY scripts/ ./scripts/
COPY config.json .

CMD ["python", "scripts/pr_labeler.py"]
```

```bash
# Build and run Docker container
docker build -t pr-labeler .
docker run -e GITHUB_TOKEN=your_token pr-labeler
```

## Best Practices

### 1. Rate Limiting

```python
# Implement exponential backoff
import random

def exponential_backoff(attempt, max_delay=300):
    """Calculate delay with exponential backoff and jitter."""
    delay = min(2 ** attempt + random.uniform(0, 1), max_delay)
    return delay

def rate_limited_request(url, **kwargs):
    """Make request with rate limiting."""
    attempt = 0
    while attempt < 5:
        try:
            response = requests.get(url, **kwargs)
            if response.status_code == 200:
                return response
            elif response.status_code == 403:
                # Rate limited
                delay = exponential_backoff(attempt)
                time.sleep(delay)
                attempt += 1
            else:
                response.raise_for_status()
        except requests.RequestException as e:
            logging.error(f"Request failed: {e}")
            break
    
    return None
```

### 2. Security

```python
# Secure token handling
def get_secure_token():
    """Get token from secure source."""
    # Priority order: environment variable, file, user input
    token = os.getenv('GITHUB_TOKEN')
    
    if not token:
        try:
            with open('.github_token', 'r') as f:
                token = f.read().strip()
        except FileNotFoundError:
            pass
    
    if not token:
        token = input("Enter GitHub token: ").strip()
    
    if not token:
        raise ValueError("GitHub token is required")
    
    return token

# Validate token permissions
def validate_token_permissions():
    """Validate that token has required permissions."""
    response = requests.get(
        'https://api.github.com/user',
        headers={'Authorization': f'token {GitHubConfig.TOKEN}'}
    )
    
    if response.status_code != 200:
        raise ValueError("Invalid GitHub token")
    
    # Check rate limits
    remaining = int(response.headers.get('X-RateLimit-Remaining', 0))
    if remaining < 100:
        logging.warning(f"Low rate limit remaining: {remaining}")
```

### 3. Monitoring

```python
import psutil
import json
from datetime import datetime

def monitor_script_performance():
    """Monitor script performance metrics."""
    start_time = datetime.now()
    start_memory = psutil.Process().memory_info().rss / 1024 / 1024  # MB
    
    # Your script logic here
    prs = obter_prs_abertos()
    # Process PRs...
    
    end_time = datetime.now()
    end_memory = psutil.Process().memory_info().rss / 1024 / 1024  # MB
    
    metrics = {
        'timestamp': datetime.now().isoformat(),
        'duration_seconds': (end_time - start_time).total_seconds(),
        'memory_usage_mb': end_memory - start_memory,
        'prs_processed': len(prs),
        'api_calls_made': len(prs) + 1  # Approximate
    }
    
    # Log metrics
    with open('performance_metrics.json', 'a') as f:
        json.dump(metrics, f)
        f.write('\n')
    
    logging.info(f"Performance metrics: {metrics}")
```

## Troubleshooting

### Common Issues

#### 1. Authentication Errors

**Problem:** 401 Unauthorized errors

**Solutions:**
```python
# Check token validity
def debug_authentication():
    response = requests.get(
        'https://api.github.com/user',
        headers={'Authorization': f'token {GitHubConfig.TOKEN}'}
    )
    
    if response.status_code == 401:
        print("Token is invalid or expired")
    elif response.status_code == 200:
        user_data = response.json()
        print(f"Authenticated as: {user_data['login']}")
    else:
        print(f"Unexpected response: {response.status_code}")
```

#### 2. Rate Limiting

**Problem:** 403 Forbidden due to rate limits

**Solutions:**
```python
# Check rate limit status
def check_rate_limits():
    response = requests.get(
        'https://api.github.com/rate_limit',
        headers=GitHubConfig.HEADERS
    )
    
    if response.status_code == 200:
        data = response.json()
        core_limit = data['resources']['core']
        print(f"Rate limit: {core_limit['remaining']}/{core_limit['limit']}")
        print(f"Reset time: {datetime.fromtimestamp(core_limit['reset'])}")
```

#### 3. Large Repository Handling

**Problem:** Script times out on large repositories

**Solutions:**
```python
# Process in batches
def process_prs_in_batches(batch_size=50):
    all_prs = obter_prs_abertos()
    
    for i in range(0, len(all_prs), batch_size):
        batch = all_prs[i:i + batch_size]
        print(f"Processing batch {i//batch_size + 1}: PRs {i+1}-{min(i+batch_size, len(all_prs))}")
        
        for pr in batch:
            # Process PR
            pass
        
        # Break between batches
        if i + batch_size < len(all_prs):
            time.sleep(30)
```

## Related Resources

- [GitHub API Documentation](https://docs.github.com/en/rest)
- [GitHub Webhooks Guide](https://docs.github.com/en/developers/webhooks-and-events/webhooks)
- [Python Requests Documentation](https://requests.readthedocs.io/)
- [Google Colab Documentation](https://colab.research.google.com/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## Contributing

Help improve the Scripts API:

1. Add new automation scripts
2. Enhance error handling
3. Improve performance optimization
4. Add new features and integrations
5. Update documentation with new examples

---

<div align="center">
  <p>Maintained by the DIO Community</p>
  <p><a href="../API_DOCUMENTATION.md">← Back to API Documentation</a></p>
</div>