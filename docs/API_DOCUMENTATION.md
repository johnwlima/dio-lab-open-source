# API Documentation - DIO Lab Open Source

<div align="center">
  <img src="https://hermes.digitalinnovation.one/assets/diome/logo-minimized.png" width="60px" alt="DIO Logo">
  <h1>Complete API Reference</h1>
  <p>Comprehensive documentation for all public APIs, functions, and components</p>
</div>

## Overview

This repository provides a comprehensive set of utilities and tools for GitHub profile enhancement, open source contribution learning, and community engagement. The APIs are organized into several modules:

- **[Utilities API](#utilities-api)** - Profile enhancement tools and helpers
- **[Scripts API](#scripts-api)** - Automation and workflow tools
- **[Community API](#community-api)** - Community contribution management
- **[Git Reference](#git-reference)** - Complete Git commands reference

## Quick Start

```bash
# Clone the repository
git clone https://github.com/digitalinnovationone/dio-lab-open-source.git

# Navigate to project directory
cd dio-lab-open-source

# Explore utilities
ls utils/
```

## API Reference

### Utilities API

The utilities module provides tools for enhancing GitHub profiles with badges, stats cards, and formatting helpers.

#### Modules

| Module | Description | Documentation |
|--------|-------------|---------------|
| [`badges`](./BADGES_API.md) | Social media and technology badges generator | [View Docs](./BADGES_API.md) |
| [`cards`](./CARDS_API.md) | GitHub statistics and profile cards | [View Docs](./CARDS_API.md) |
| [`markdown`](./MARKDOWN_API.md) | Markdown syntax utilities and helpers | [View Docs](./MARKDOWN_API.md) |
| [`git`](./GIT_API.md) | Git commands reference and utilities | [View Docs](./GIT_API.md) |

#### Quick Examples

```markdown
<!-- Add a LinkedIn badge -->
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)

<!-- Display GitHub stats -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&theme=transparent&bg_color=000&border_color=30A3DC&show_icons=true)
```

### Scripts API

Automation tools and workflow helpers for repository management.

#### PR Labeler Script

**File:** `scripts/PR_Labeler_DIO_Lab_Workflow_Trigger.ipynb`

Automated pull request labeling and workflow triggering system.

| Component | Type | Description |
|-----------|------|-------------|
| `GitHubConfig` | Class | GitHub API configuration and authentication |
| `ScriptConfig` | Class | Script-specific configuration settings |
| `obter_prs_abertos()` | Function | Retrieves all open pull requests |
| `aplicar_label_em_pr()` | Function | Applies labels to pull requests |
| `main()` | Function | Main execution flow |

**[View Complete Documentation](./SCRIPTS_API.md)**

### Community API

Community contribution management and profile organization system.

#### Profile Management

The community directory contains contributor profiles organized alphabetically.

**Structure:**
```
community/
├── [username].md     # Individual contributor profiles
└── README.md         # Community guidelines
```

**[View Complete Documentation](./COMMUNITY_API.md)**

## Usage Examples

### Basic Badge Integration

```markdown
<!-- Technology stack badges -->
![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python)
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
![React](https://img.shields.io/badge/React-000?style=for-the-badge&logo=react)
```

### GitHub Stats Cards

```markdown
<!-- Basic stats card -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&theme=transparent&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)

<!-- Most used languages -->
![Top Langs](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=yourusername&layout=compact&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)
```

### Git Workflow

```bash
# Basic contribution workflow
git clone [repository-url]
git checkout -b feature/new-contribution
git add .
git commit -m "feat: add new contribution"
git push origin feature/new-contribution
```

## Advanced Usage

### Custom Badge Creation

Create custom badges using the Shields.io API:

```markdown
![Custom Badge](https://img.shields.io/badge/Custom-Message-color?style=for-the-badge&logo=icon&logoColor=white)
```

**Parameters:**
- `Custom`: Badge label
- `Message`: Badge message
- `color`: Background color (hex or named)
- `style`: Badge style (flat, flat-square, for-the-badge, etc.)
- `logo`: Icon name from Simple Icons
- `logoColor`: Icon color

### GitHub Stats Customization

**Available Parameters:**

| Parameter | Description | Default |
|-----------|-------------|---------|
| `username` | GitHub username | required |
| `theme` | Color theme | default |
| `bg_color` | Background color | transparent |
| `border_color` | Border color | theme default |
| `title_color` | Title text color | theme default |
| `text_color` | Body text color | theme default |
| `icon_color` | Icon color | theme default |
| `show_icons` | Display icons | false |
| `hide` | Hide specific stats | none |
| `count_private` | Count private repos | false |

## Best Practices

### 1. Badge Organization

Group badges by category for better readability:

```markdown
## 🌐 Connect with me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](your-linkedin)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github)](your-github)

## 💻 Tech Stack
![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python)
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
```

### 2. Consistent Styling

Use consistent color schemes across all elements:

```markdown
<!-- DIO Theme Colors -->
<!-- Primary: #30A3DC (Blue) -->
<!-- Secondary: #E94D5F (Red) -->
<!-- Background: #000 (Black) -->
<!-- Text: #FFF (White) -->
```

### 3. Performance Optimization

- Use `layout=compact` for language stats in limited space
- Cache stats cards by avoiding frequent username changes
- Use appropriate image formats and sizes

## Error Handling

### Common Issues

1. **Badge not displaying**: Check URL encoding and parameter syntax
2. **Stats card errors**: Verify username and GitHub API limits
3. **Git command failures**: Check repository permissions and network connectivity

### Troubleshooting

```bash
# Test GitHub API connectivity
curl -H "Accept: application/vnd.github.v3+json" https://api.github.com/users/yourusername

# Verify Git configuration
git config --list

# Check repository status
git status
git remote -v
```

## Contributing

### Adding New Utilities

1. Create utility file in appropriate `utils/` subdirectory
2. Add documentation following the established format
3. Include usage examples and parameter descriptions
4. Update this main documentation index

### Documentation Standards

- Use clear, descriptive headings
- Include practical examples for all features
- Document all parameters and return values
- Provide troubleshooting information
- Follow consistent markdown formatting

## Support

- **Documentation Issues**: Open an issue with the `documentation` label
- **Feature Requests**: Open an issue with the `enhancement` label
- **Bug Reports**: Open an issue with the `bug` label

## License

This project is licensed under the MIT License. See the [LICENSE](../LICENSE) file for details.

---

<div align="center">
  <p>Made with ❤️ by the DIO Community</p>
  <p><a href="https://www.dio.me/">Digital Innovation One</a> • <a href="https://github.com/digitalinnovationone/dio-lab-open-source">GitHub Repository</a></p>
</div>