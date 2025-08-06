# Community API Documentation

<div align="center">
  <img src="https://img.shields.io/badge/Community-API-7B68EE?style=for-the-badge&logo=github&logoColor=white" alt="Community API">
  <h1>Community Contribution System API</h1>
  <p>Guidelines and tools for open source community participation</p>
</div>

## Overview

The Community API provides the structure and guidelines for contributing to the open source community through profile submissions, collaboration, and knowledge sharing. This system manages contributor profiles organized in the [`community/`](../community/) directory.

**Purpose:** Learn Git/GitHub workflows through practical contribution  
**Structure:** Individual contributor profiles in Markdown format  
**Organization:** Alphabetical filing system by username  
**Learning Focus:** Open source collaboration, Git workflows, Markdown formatting

## Community Structure

### Directory Organization

```
community/
├── [username].md          # Individual contributor profiles
├── README.md              # Community guidelines
└── [thousands of profiles] # Alphabetically organized
```

### Profile Naming Convention

```bash
# Format: [github-username].md
# Examples:
falvojr.md                 # Username: falvojr
harryazawa.md             # Username: harryazawa
AlexandreRobaert.md       # Username: AlexandreRobaert
```

**Rules:**
- File name must match GitHub username exactly
- Use `.md` extension
- Case-sensitive naming
- No spaces or special characters beyond those in username

## Profile Structure API

### Basic Profile Template

```markdown
### Olá, eu sou [Seu Nome] ([username]) 👋

✨ [Breve descrição profissional]

🏢 **Atuação Profissional**
- 🚀 [Cargo atual]
- 🎓 [Formação ou estudos]

### 📊 Estatísticas no GitHub

![username's GitHub stats](https://github-readme-stats.vercel.app/api?username=username&show_icons=true&theme=dracula)

### 🚀 Linguagens Mais Usadas

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=username&layout=compact)

### 📌 Projetos em Destaque

[![Repo Name](https://github-readme-stats.vercel.app/api/pin/?username=username&repo=repository-name)](https://github.com/username/repository-name)

### 🌐 Conecte-se comigo

[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github)](https://github.com/yourusername)
```

### Profile Sections

#### 1. Header Section

```markdown
### Olá, eu sou [Nome] ([username]) 👋

✨ **[Título/Posição]** - [Descrição breve]
```

**Components:**
- Greeting with name and username
- Professional title or study focus
- Brief description of background
- Emoji usage for visual appeal

#### 2. Professional Information

```markdown
🏢 **Atuação Profissional**
- 🚀 [Current Role/Company]
- 🎓 [Education/Studies]
- 💼 [Additional roles]
- 📚 [Learning focus]
```

**Best Practices:**
- Use emojis consistently
- List current roles first
- Include educational background
- Mention learning goals

#### 3. GitHub Statistics

```markdown
### 📊 Estatísticas no GitHub

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true&theme=dracula)
```

**Available Themes:**
- `dracula` - Dark theme with purple accents
- `jolly` - Green and orange theme
- `transparent` - Transparent background
- `dark` - Dark mode
- `radical` - Pink and blue theme

**Parameters:**
- `show_icons=true` - Display category icons
- `include_all_commits=true` - Count all commits
- `count_private=true` - Include private repositories

#### 4. Programming Languages

```markdown
### 🚀 Linguagens Mais Usadas

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact)
```

**Layout Options:**
- `compact` - Horizontal compact layout
- `default` - Vertical detailed layout

**Customization:**
- `langs_count=7` - Number of languages to show
- `theme=jolly` - Color theme matching stats
- `hide=html,css` - Hide specific languages

#### 5. Technology Stack

```markdown
<div align="left" style="display: inline_block">
  <h4>Tech Stack</h4>
  <img align="center" alt="JavaScript" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg"/>
  <img align="center" alt="Python" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg"/>
  <img align="center" alt="React" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg"/>
</div>
```

**Icon Sources:**
- [DevIcons](https://github.com/devicons/devicon/tree/master/icons) - Technology icons
- [Simple Icons](https://simpleicons.org/) - Brand icons
- Custom SVG icons for specific technologies

#### 6. Featured Projects

```markdown
### 📌 Projetos em Destaque

[![Project Name](https://github-readme-stats.vercel.app/api/pin/?username=yourusername&repo=project-name)](https://github.com/yourusername/project-name)
```

**Best Practices:**
- Showcase 1-3 most important projects
- Use descriptive project names
- Link directly to repositories
- Choose projects that demonstrate skills

#### 7. Contact Information

```markdown
### 🌐 Conecte-se comigo

[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://linkedin.com/in/yourprofile)
[![Email](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF)](mailto:your@email.com)
```

**Available Platforms:**
- LinkedIn (professional networking)
- GitHub (code repositories)
- Twitter (social updates)
- Email (direct contact)
- Portfolio website
- Discord (community chat)

## Contribution Workflow

### 1. Fork and Clone

```bash
# 1. Fork the repository on GitHub
# 2. Clone your fork
git clone https://github.com/yourusername/dio-lab-open-source.git

# 3. Navigate to project directory
cd dio-lab-open-source

# 4. Add upstream remote
git remote add upstream https://github.com/digitalinnovationone/dio-lab-open-source.git
```

### 2. Create Profile

```bash
# 1. Create your profile file
touch community/yourusername.md

# 2. Edit with your preferred editor
code community/yourusername.md
# or
nano community/yourusername.md
```

### 3. Submit Contribution

```bash
# 1. Create feature branch
git checkout -b feat/community-yourusername

# 2. Add your profile
git add community/yourusername.md

# 3. Commit with conventional format
git commit -m "feat: add yourusername community profile"

# 4. Push to your fork
git push origin feat/community-yourusername

# 5. Create pull request on GitHub
```

### 4. Pull Request Guidelines

#### PR Title Format

```
feat: add [username] community profile
```

#### PR Description Template

```markdown
## 📋 Descrição

Adicionando meu perfil à comunidade DIO.

## 🔗 Informações do Perfil

- **GitHub:** [@yourusername](https://github.com/yourusername)
- **LinkedIn:** [Seu Nome](https://linkedin.com/in/yourprofile)
- **Área de Interesse:** [Frontend/Backend/Data Science/etc.]

## ✅ Checklist

- [x] Segui o formato do template
- [x] Incluí informações relevantes
- [x] Testei os links
- [x] Usei emojis adequadamente
- [x] Arquivo nomeado corretamente
```

### 5. Review Process

**Automated Checks:**
- File naming validation
- Markdown syntax validation
- Link verification
- Image loading verification

**Manual Review:**
- Content appropriateness
- Template adherence
- Professional presentation
- Community guidelines compliance

## Advanced Profile Features

### 1. Dynamic Statistics

```markdown
<!-- GitHub Activity Graph -->
[![GitHub Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=yourusername&theme=dracula)](https://github.com/yourusername)

<!-- Contribution Streak -->
[![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername&theme=dracula)](https://git.io/streak-stats)

<!-- Profile Views Counter -->
![Profile Views](https://komarev.com/ghpvc/?username=yourusername&color=blueviolet)
```

### 2. Animated Elements

```markdown
<!-- Typing Animation -->
[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=36BCF7&width=435&lines=Full+Stack+Developer;Always+learning+new+things)](https://git.io/typing-svg)

<!-- Wave Animation -->
<img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">
```

### 3. Custom Layouts

```markdown
<div align="center">
  
  <!-- Side-by-side stats -->
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true&theme=dracula"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact&theme=dracula"/>
  
</div>

<!-- Three-column layout -->
<table>
  <tr>
    <td>🚀 Projects</td>
    <td>📊 Stats</td>
    <td>🛠️ Skills</td>
  </tr>
  <tr>
    <td>Project list</td>
    <td>GitHub stats</td>
    <td>Technology icons</td>
  </tr>
</table>
```

### 4. Interactive Elements

```markdown
<!-- Collapsible sections -->
<details>
  <summary>🎯 Objetivos 2024</summary>
  
  - [ ] Aprender React Native
  - [ ] Contribuir para 5 projetos open source
  - [ ] Completar certificação AWS
  - [x] Criar meu primeiro projeto full-stack
  
</details>

<details>
  <summary>📚 Estudos Atuais</summary>
  
  - **Frontend:** React, Next.js, TypeScript
  - **Backend:** Node.js, Python, PostgreSQL
  - **DevOps:** Docker, AWS, CI/CD
  
</details>
```

## Community Guidelines

### 1. Content Standards

**Allowed Content:**
- Professional information
- Technical skills and interests
- Educational background
- Project showcases
- Contact information
- Learning goals

**Prohibited Content:**
- Personal political opinions
- Inappropriate images or language
- Spam or promotional content
- False or misleading information
- Copyright violations

### 2. Technical Requirements

**File Format:**
- Markdown (.md) files only
- UTF-8 encoding
- Unix line endings (LF)
- Maximum file size: 1MB

**Image Guidelines:**
- Use external image hosting (GitHub, CDN)
- Optimize image sizes for web
- Provide alt text for accessibility
- Use HTTPS URLs only

**Link Requirements:**
- All links must be functional
- Use HTTPS when available
- No broken or redirect chains
- Test links before submission

### 3. Accessibility Standards

```markdown
<!-- Good: Descriptive alt text -->
![GitHub stats showing commit activity and language distribution](stats-url)

<!-- Bad: Missing or generic alt text -->
![](stats-url)
![image](stats-url)

<!-- Good: Meaningful link text -->
[View my portfolio website](https://portfolio.com)

<!-- Bad: Generic link text -->
[Click here](https://portfolio.com)
```

### 4. Professional Presentation

**Best Practices:**
- Use consistent formatting
- Maintain professional tone
- Include accurate information
- Regular profile updates
- Responsive design consideration

**Common Mistakes:**
- Excessive emoji usage
- Unprofessional language
- Broken links or images
- Inconsistent styling
- Missing contact information

## Quality Assurance

### 1. Pre-submission Checklist

```markdown
## ✅ Profile Quality Checklist

### Content
- [ ] Professional greeting and introduction
- [ ] Clear role/study information
- [ ] Relevant technical skills
- [ ] Working contact links
- [ ] Proper grammar and spelling

### Technical
- [ ] File named correctly (username.md)
- [ ] Valid Markdown syntax
- [ ] All images load properly
- [ ] All links are functional
- [ ] Consistent formatting

### Professional
- [ ] Appropriate content only
- [ ] Professional language
- [ ] Accurate information
- [ ] Good visual organization
- [ ] Mobile-friendly layout
```

### 2. Testing Tools

```bash
# Markdown validation
markdownlint community/yourusername.md

# Link checking
markdown-link-check community/yourusername.md

# Preview locally
grip community/yourusername.md
```

### 3. Common Issues and Solutions

#### Issue: Images Not Loading

**Problem:** External images showing as broken

**Solutions:**
```markdown
<!-- Use reliable CDNs -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername)

<!-- GitHub raw URLs for personal images -->
![Avatar](https://raw.githubusercontent.com/yourusername/yourusername/main/avatar.png)

<!-- Check image URLs before commit -->
curl -I "https://image-url.com/image.png"
```

#### Issue: Stats Cards Not Updating

**Problem:** GitHub stats showing outdated information

**Solutions:**
```markdown
<!-- Add cache busting parameter -->
![Stats](https://github-readme-stats.vercel.app/api?username=yourusername&v=1)

<!-- Use alternative endpoints -->
![Stats](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api?username=yourusername)
```

#### Issue: Inconsistent Layout

**Problem:** Profile layout breaks on different screen sizes

**Solutions:**
```markdown
<!-- Use responsive image sizes -->
<img height="180em" width="400em" src="stats-url" style="max-width: 100%;">

<!-- Center align for mobile -->
<div align="center">
  <img src="stats-url" style="max-width: 100%;">
</div>
```

## API Integration Examples

### 1. Profile Generation Script

```python
def generate_profile_template(username, name, role, technologies):
    """Generate a community profile template."""
    template = f"""### Olá, eu sou {name} ({username}) 👋

✨ **{role}**

🏢 **Foco atual:**
{' '.join([f'![{tech}](badge-url-for-{tech.lower()})' for tech in technologies])}

### 📊 Estatísticas no GitHub

![{username}'s GitHub stats](https://github-readme-stats.vercel.app/api?username={username}&show_icons=true&theme=dracula)

### 🚀 Linguagens Mais Usadas

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username={username}&layout=compact)

### 🌐 Conecte-se comigo

[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github)](https://github.com/{username})
"""
    return template

# Usage
profile = generate_profile_template(
    username="johndoe",
    name="João Silva",
    role="Desenvolvedor Full Stack",
    technologies=["JavaScript", "Python", "React", "Node.js"]
)

with open(f"community/johndoe.md", "w") as f:
    f.write(profile)
```

### 2. Profile Validation Script

```python
import re
import requests
from pathlib import Path

def validate_community_profile(filepath):
    """Validate a community profile for compliance."""
    
    profile_path = Path(filepath)
    
    # Check filename format
    if not re.match(r'^[a-zA-Z0-9_-]+\.md$', profile_path.name):
        return False, "Invalid filename format"
    
    # Read content
    try:
        content = profile_path.read_text(encoding='utf-8')
    except UnicodeDecodeError:
        return False, "Invalid encoding (must be UTF-8)"
    
    # Check required sections
    required_sections = [
        r'###.*👋',  # Greeting header
        r'📊.*GitHub',  # Stats section
        r'🚀.*Linguagens',  # Languages section
    ]
    
    for pattern in required_sections:
        if not re.search(pattern, content, re.IGNORECASE):
            return False, f"Missing required section: {pattern}"
    
    # Validate GitHub stats URLs
    github_urls = re.findall(r'https://github-readme-stats[^)]+', content)
    for url in github_urls:
        try:
            response = requests.head(url, timeout=10)
            if response.status_code != 200:
                return False, f"Broken GitHub stats URL: {url}"
        except requests.RequestException:
            return False, f"Unable to verify URL: {url}"
    
    return True, "Profile validation passed"

# Usage
is_valid, message = validate_community_profile("community/johndoe.md")
print(f"Validation result: {message}")
```

### 3. Community Analytics

```python
import os
import re
from collections import Counter

def analyze_community_profiles():
    """Analyze community profiles for insights."""
    
    community_dir = Path("community")
    profiles = list(community_dir.glob("*.md"))
    
    analytics = {
        'total_profiles': len(profiles),
        'technologies': Counter(),
        'roles': Counter(),
        'themes': Counter()
    }
    
    for profile_path in profiles:
        content = profile_path.read_text(encoding='utf-8')
        
        # Extract technologies from badges
        tech_badges = re.findall(r'devicons/devicon/[^/]+/icons/([^/]+)/', content)
        analytics['technologies'].update(tech_badges)
        
        # Extract roles/titles
        role_matches = re.findall(r'\*\*([^*]+)\*\*', content)
        analytics['roles'].update(role_matches)
        
        # Extract GitHub stats themes
        theme_matches = re.findall(r'theme=([^&\)]+)', content)
        analytics['themes'].update(theme_matches)
    
    return analytics

# Generate report
stats = analyze_community_profiles()
print(f"Community Analytics:")
print(f"Total Profiles: {stats['total_profiles']}")
print(f"Top Technologies: {stats['technologies'].most_common(10)}")
print(f"Popular Themes: {stats['themes'].most_common(5)}")
```

## Best Practices

### 1. Profile Maintenance

```markdown
<!-- Regular updates recommended -->
- Update skills as you learn new technologies
- Add new projects to featured section
- Keep contact information current
- Update role/status changes
- Refresh GitHub stats themes seasonally
```

### 2. SEO and Discoverability

```markdown
<!-- Use descriptive headings -->
### 🚀 JavaScript Developer & React Enthusiast

<!-- Include relevant keywords -->
Especialista em desenvolvimento **frontend** com **React**, **TypeScript**, e **Next.js**.

<!-- Tag technologies clearly -->
**Tech Stack:** `JavaScript` `React` `Node.js` `PostgreSQL`
```

### 3. Community Engagement

```markdown
<!-- Link to contributions -->
### 🤝 Contribuições Open Source

- [Project Name](https://github.com/org/project) - Descrição da contribuição
- [Another Project](https://github.com/org/project2) - Feature implementada

<!-- Showcase collaboration -->
### 👥 Colaborações

- **Mentor** no programa DIO
- **Contribuidor** em projetos da comunidade
- **Organizador** de eventos locais
```

## Related Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub README Stats](https://github.com/anuraghazra/github-readme-stats)
- [DevIcons](https://github.com/devicons/devicon)
- [Shields.io](https://shields.io/)
- [GitHub Profile Examples](https://github.com/abhisheknaiidu/awesome-github-profile-readme)

## Contributing to Community API

Help improve the community system:

1. **Profile Templates:** Create new profile templates for different roles
2. **Validation Tools:** Enhance profile validation scripts
3. **Documentation:** Improve guidelines and examples
4. **Automation:** Build tools for easier profile creation
5. **Analytics:** Develop community insights and statistics

### Enhancement Ideas

```markdown
## Potential Enhancements

### 1. Profile Templates by Role
- Frontend Developer template
- Data Scientist template
- DevOps Engineer template
- Student/Beginner template

### 2. Interactive Features
- Profile galleries by technology
- Community skill mapping
- Collaboration finder

### 3. Quality Tools
- Automated link checking
- Image optimization
- Accessibility validation
- Performance monitoring
```

---

<div align="center">
  <p>Maintained by the DIO Community</p>
  <p><a href="../API_DOCUMENTATION.md">← Back to API Documentation</a></p>
</div>