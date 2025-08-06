# Badges API Documentation

<div align="center">
  <img src="https://img.shields.io/badge/Badges-API-30A3DC?style=for-the-badge&logo=shield&logoColor=white" alt="Badges API">
  <h1>Badges Utility API</h1>
  <p>Comprehensive reference for badge generation and customization</p>
</div>

## Overview

The Badges API provides a comprehensive collection of pre-configured badges for enhancing GitHub profiles and documentation. All badges are generated using the [Shields.io](https://shields.io/) service and follow consistent styling patterns optimized for the DIO theme.

**Source:** [`utils/badges/badges.md`](../utils/badges/badges.md)  
**Generator:** [Shields.io](https://shields.io/)  
**Repository:** [badges/shields](https://github.com/badges/shields)

## Quick Start

```markdown
<!-- Basic badge usage -->
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)

<!-- Technology stack -->
![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python)
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
```

## Badge Categories

### 1. Social Media Badges

Connect with your audience through social platforms.

| Badge | Usage | Link Template |
|-------|-------|---------------|
| ![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8) | Professional networking | `https://www.linkedin.com/in/YOURUSERNAME/` |
| ![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github) | Code repository | `https://github.com/YOURUSERNAME` |
| ![Discord](https://img.shields.io/badge/Discord-000?style=for-the-badge&logo=discord) | Community chat | `https://discord.com/channels/@YOURUSERNAME/` |
| ![Twitter](https://img.shields.io/badge/Twitter-000?style=for-the-badge&logo=twitter) | Social updates | `https://twitter.com/YOURUSERNAME` |
| ![Instagram](https://img.shields.io/badge/Instagram-000?style=for-the-badge&logo=instagram) | Visual content | `https://www.instagram.com/YOURUSERNAME/` |
| ![Facebook](https://img.shields.io/badge/Facebook-000?style=for-the-badge&logo=facebook) | Social networking | `https://www.facebook.com/YOURUSERNAME/` |
| ![Telegram](https://img.shields.io/badge/Telegram-000?style=for-the-badge&logo=telegram&logoColor=2CA5E0) | Messaging | `https://t.me/YOURUSERNAME` |
| ![Reddit](https://img.shields.io/badge/Reddit-000?style=for-the-badge&logo=reddit&logoColor=FF4500) | Community discussions | `https://www.reddit.com/u/YOURUSERNAME` |
| ![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white) | Direct messaging | `https://wa.me/DDI+DDD+YOURNUMBER` |
| ![Email](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF) | Contact | `mailto:YOUREMAIL` |

#### Example Implementation

```markdown
## 🌐 Connect with me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github)](https://github.com/yourusername)
[![Discord](https://img.shields.io/badge/Discord-000?style=for-the-badge&logo=discord)](https://discord.com/channels/@yourusername/)
[![Email](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF)](mailto:your@email.com)
```

### 2. Programming Languages

Showcase your programming language expertise.

| Language | Badge | Markdown Code |
|----------|-------|---------------|
| JavaScript | ![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript) | `![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)` |
| TypeScript | ![TypeScript](https://img.shields.io/badge/TypeScript-000?style=for-the-badge&logo=typescript) | `![TypeScript](https://img.shields.io/badge/TypeScript-000?style=for-the-badge&logo=typescript)` |
| Python | ![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python) | `![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python)` |
| Java | ![Java](https://img.shields.io/badge/Java-000?style=for-the-badge&logo=java) | `![Java](https://img.shields.io/badge/Java-000?style=for-the-badge&logo=java)` |
| C++ | ![C++](https://img.shields.io/badge/C++-000?style=for-the-badge&logo=c%2B%2B&logoColor=00599C) | `![C++](https://img.shields.io/badge/C++-000?style=for-the-badge&logo=c%2B%2B&logoColor=00599C)` |
| C# | ![C#](https://img.shields.io/badge/C%23-000?style=for-the-badge&logo=c-sharp&logoColor=239120) | `![C#](https://img.shields.io/badge/C%23-000?style=for-the-badge&logo=c-sharp&logoColor=239120)` |
| PHP | ![PHP](https://img.shields.io/badge/PHP-000?style=for-the-badge&logo=php&logoColor=777884) | `![PHP](https://img.shields.io/badge/PHP-000?style=for-the-badge&logo=php&logoColor=777884)` |
| Go | ![Go](https://img.shields.io/badge/Go-000?style=for-the-badge&logo=go) | `![Go](https://img.shields.io/badge/Go-000?style=for-the-badge&logo=go)` |
| Rust | ![Rust](https://img.shields.io/badge/Rust-000?style=for-the-badge&logo=rust&logoColor=white) | `![Rust](https://img.shields.io/badge/Rust-000?style=for-the-badge&logo=rust&logoColor=white)` |
| Swift | ![Swift](https://img.shields.io/badge/Swift-000?style=for-the-badge&logo=swift) | `![Swift](https://img.shields.io/badge/Swift-000?style=for-the-badge&logo=swift)` |

### 3. Markup & Styling Languages

Display your frontend and markup skills.

| Technology | Badge | Markdown Code |
|------------|-------|---------------|
| HTML5 | ![HTML5](https://img.shields.io/badge/HTML5-000?style=for-the-badge&logo=html5) | `![HTML5](https://img.shields.io/badge/HTML5-000?style=for-the-badge&logo=html5)` |
| CSS3 | ![CSS3](https://img.shields.io/badge/CSS3-000?style=for-the-badge&logo=css3&logoColor=264CE4) | `![CSS3](https://img.shields.io/badge/CSS3-000?style=for-the-badge&logo=css3&logoColor=264CE4)` |
| Sass | ![Sass](https://img.shields.io/badge/Sass-000?style=for-the-badge&logo=sass) | `![Sass](https://img.shields.io/badge/Sass-000?style=for-the-badge&logo=sass)` |
| Markdown | ![Markdown](https://img.shields.io/badge/Markdown-000?style=for-the-badge&logo=markdown) | `![Markdown](https://img.shields.io/badge/Markdown-000?style=for-the-badge&logo=markdown)` |

### 4. Frameworks & Libraries

Highlight your framework expertise.

| Framework | Badge | Markdown Code |
|-----------|-------|---------------|
| React | ![React](https://img.shields.io/badge/React-000?style=for-the-badge&logo=react) | `![React](https://img.shields.io/badge/React-000?style=for-the-badge&logo=react)` |
| Vue.js | ![Vue.js](https://img.shields.io/badge/Vue.js-000?style=for-the-badge&logo=vue.js) | `![Vue.js](https://img.shields.io/badge/Vue.js-000?style=for-the-badge&logo=vue.js)` |
| Angular | ![Angular](https://img.shields.io/badge/Angular-000?style=for-the-badge&logo=angular&logoColor=C3002F) | `![Angular](https://img.shields.io/badge/Angular-000?style=for-the-badge&logo=angular&logoColor=C3002F)` |
| Node.js | ![Node.js](https://img.shields.io/badge/Node.js-000?style=for-the-badge&logo=node.js) | `![Node.js](https://img.shields.io/badge/Node.js-000?style=for-the-badge&logo=node.js)` |
| Express | ![Express](https://img.shields.io/badge/Express-000?style=for-the-badge&logo=express) | `![Express](https://img.shields.io/badge/Express-000?style=for-the-badge&logo=express)` |
| Flutter | ![Flutter](https://img.shields.io/badge/Flutter-000?style=for-the-badge&logo=flutter&logoColor=02569B) | `![Flutter](https://img.shields.io/badge/Flutter-000?style=for-the-badge&logo=flutter&logoColor=02569B)` |

### 5. Databases

Show your data management capabilities.

| Database | Badge | Markdown Code |
|----------|-------|---------------|
| MySQL | ![MySQL](https://img.shields.io/badge/MySQL-000?style=for-the-badge&logo=mysql&logoColor=005C84) | `![MySQL](https://img.shields.io/badge/MySQL-000?style=for-the-badge&logo=mysql&logoColor=005C84)` |
| PostgreSQL | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-000?style=for-the-badge&logo=postgresql) | `![PostgreSQL](https://img.shields.io/badge/PostgreSQL-000?style=for-the-badge&logo=postgresql)` |
| SQLite | ![SQLite](https://img.shields.io/badge/SQLite-000?style=for-the-badge&logo=sqlite&logoColor=07405E) | `![SQLite](https://img.shields.io/badge/SQLite-000?style=for-the-badge&logo=sqlite&logoColor=07405E)` |
| MongoDB | ![MongoDB](https://img.shields.io/badge/MongoDB-000?style=for-the-badge&logo=mongodb) | `![MongoDB](https://img.shields.io/badge/MongoDB-000?style=for-the-badge&logo=mongodb)` |

### 6. Cloud & Services

Display your cloud platform experience.

| Service | Badge | Markdown Code |
|---------|-------|---------------|
| Firebase | ![Firebase](https://img.shields.io/badge/Firebase-000?style=for-the-badge&logo=firebase&logoColor=ffca28) | `![Firebase](https://img.shields.io/badge/Firebase-000?style=for-the-badge&logo=firebase&logoColor=ffca28)` |
| Azure | ![Azure](https://img.shields.io/badge/Azure-blue?style=for-the-badge&logo=microsoft%20azure&logoColor=blue&labelColor=FFFFFF) | `![Azure](https://img.shields.io/badge/Azure-blue?style=for-the-badge&logo=microsoft%20azure&logoColor=blue&labelColor=FFFFFF)` |
| AWS | ![AWS](https://img.shields.io/badge/AWS-000?style=for-the-badge&logo=amazon-aws&logoColor=FF9900) | `![AWS](https://img.shields.io/badge/AWS-000?style=for-the-badge&logo=amazon-aws&logoColor=FF9900)` |

### 7. Operating Systems

Show your platform compatibility.

| OS | Badge | Markdown Code |
|----|-------|---------------|
| Linux | ![Linux](https://img.shields.io/badge/Linux-000?style=for-the-badge&logo=linux&logoColor=FCC624) | `![Linux](https://img.shields.io/badge/Linux-000?style=for-the-badge&logo=linux&logoColor=FCC624)` |
| Windows | ![Windows](https://img.shields.io/badge/Windows-000?style=for-the-badge&logo=windows&logoColor=2CA5E0) | `![Windows](https://img.shields.io/badge/Windows-000?style=for-the-badge&logo=windows&logoColor=2CA5E0)` |
| macOS | ![macOS](https://img.shields.io/badge/macOS-000?style=for-the-badge&logo=apple&logoColor=white) | `![macOS](https://img.shields.io/badge/macOS-000?style=for-the-badge&logo=apple&logoColor=white)` |

## Advanced Customization

### Badge Parameters

All badges support these customization parameters:

| Parameter | Description | Default | Example |
|-----------|-------------|---------|---------|
| `style` | Badge style | `flat` | `for-the-badge`, `flat-square`, `plastic` |
| `logo` | Icon from Simple Icons | none | `javascript`, `python`, `react` |
| `logoColor` | Icon color | auto | `white`, `black`, `#FF0000` |
| `label` | Left side text | auto | Custom label text |
| `message` | Right side text | auto | Custom message text |
| `color` | Background color | `brightgreen` | `blue`, `red`, `#30A3DC` |
| `labelColor` | Label background | auto | `black`, `white`, `#000000` |

### Custom Badge Creation

Create completely custom badges using the Shields.io API:

```markdown
<!-- Basic custom badge -->
![Custom](https://img.shields.io/badge/Custom-Message-color?style=for-the-badge)

<!-- Badge with icon -->
![Custom](https://img.shields.io/badge/Framework-React-61DAFB?style=for-the-badge&logo=react&logoColor=white)

<!-- Badge with custom colors -->
![Custom](https://img.shields.io/badge/Status-Active-success?style=for-the-badge&labelColor=000&color=30A3DC)
```

### DIO Theme Colors

Use these official DIO colors for consistent branding:

```markdown
<!-- Primary Colors -->
Primary Blue: #30A3DC
Secondary Red: #E94D5F
Background: #000000
Text: #FFFFFF

<!-- Usage Example -->
![DIO](https://img.shields.io/badge/DIO-Community-30A3DC?style=for-the-badge&logo=github&logoColor=white)
```

## Usage Examples

### Complete Profile Section

```markdown
## 💻 Tech Stack
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
![TypeScript](https://img.shields.io/badge/TypeScript-000?style=for-the-badge&logo=typescript)
![React](https://img.shields.io/badge/React-000?style=for-the-badge&logo=react)
![Node.js](https://img.shields.io/badge/Node.js-000?style=for-the-badge&logo=node.js)

## 🛢️ Database
![MySQL](https://img.shields.io/badge/MySQL-000?style=for-the-badge&logo=mysql&logoColor=005C84)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-000?style=for-the-badge&logo=postgresql)

## ☁️ Cloud & Tools
![AWS](https://img.shields.io/badge/AWS-000?style=for-the-badge&logo=amazon-aws&logoColor=FF9900)
![Docker](https://img.shields.io/badge/Docker-000?style=for-the-badge&logo=docker)

## 🌐 Connect with me
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/yourprofile/)
[![GitHub](https://img.shields.io/badge/GitHub-000?style=for-the-badge&logo=github)](https://github.com/yourusername)
```

### Organized by Categories

```markdown
<div align="center">

## 🚀 Languages & Technologies

### Frontend
![HTML5](https://img.shields.io/badge/HTML5-000?style=for-the-badge&logo=html5)
![CSS3](https://img.shields.io/badge/CSS3-000?style=for-the-badge&logo=css3&logoColor=264CE4)
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
![React](https://img.shields.io/badge/React-000?style=for-the-badge&logo=react)

### Backend
![Node.js](https://img.shields.io/badge/Node.js-000?style=for-the-badge&logo=node.js)
![Python](https://img.shields.io/badge/Python-000?style=for-the-badge&logo=python)
![Express](https://img.shields.io/badge/Express-000?style=for-the-badge&logo=express)

### Database
![MySQL](https://img.shields.io/badge/MySQL-000?style=for-the-badge&logo=mysql&logoColor=005C84)
![MongoDB](https://img.shields.io/badge/MongoDB-000?style=for-the-badge&logo=mongodb)

</div>
```

## API Functions

### Badge Generation

```javascript
// Programmatic badge generation (for documentation)
function generateBadge(technology, color = '000', logo = null) {
  const baseUrl = 'https://img.shields.io/badge/';
  const params = new URLSearchParams({
    style: 'for-the-badge',
    logo: logo || technology.toLowerCase(),
    logoColor: 'white'
  });
  
  return `![${technology}](${baseUrl}${technology}-${color}?${params})`;
}

// Usage
console.log(generateBadge('React', '61DAFB', 'react'));
// Output: ![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=white)
```

### Badge Validation

```javascript
// Validate badge URL structure
function validateBadgeUrl(url) {
  const badgePattern = /^https:\/\/img\.shields\.io\/badge\//;
  return badgePattern.test(url);
}

// Check for required parameters
function checkBadgeParameters(url) {
  const requiredParams = ['style'];
  const urlObj = new URL(url);
  
  return requiredParams.every(param => 
    urlObj.searchParams.has(param)
  );
}
```

## Best Practices

### 1. Consistent Styling

- Always use `style=for-the-badge` for profile badges
- Maintain consistent color scheme across all badges
- Use official brand colors when available

### 2. Logical Organization

- Group related technologies together
- Use section headers for better readability
- Limit the number of badges per section (5-8 recommended)

### 3. Accessibility

- Ensure sufficient color contrast
- Use descriptive alt text
- Test with screen readers

### 4. Performance

- Use consistent badge services to leverage browser caching
- Avoid excessive badge counts on single pages
- Consider lazy loading for large badge collections

## Troubleshooting

### Common Issues

1. **Badge not displaying**
   - Check URL encoding for special characters
   - Verify logo name exists in Simple Icons
   - Ensure proper parameter syntax

2. **Incorrect colors**
   - Use hex codes without the `#` symbol
   - Check color parameter spelling
   - Verify logoColor is compatible with background

3. **Missing icons**
   - Verify icon name matches Simple Icons database
   - Use URL encoding for special characters
   - Check for typos in logo parameter

### Debug Tools

```bash
# Test badge URL
curl -I "https://img.shields.io/badge/Test-Badge-blue?style=for-the-badge"

# Validate Simple Icons availability
curl "https://simple-icons.dev/icons.json" | grep "iconname"
```

## Contributing

To add new badge categories or improve existing ones:

1. Fork the repository
2. Add badges to `utils/badges/badges.md`
3. Follow the established table format
4. Update this documentation
5. Submit a pull request

### Badge Submission Format

```markdown
| Badge | Markdown |
|-------|----------|
| ![TechnologyName](badge-url) | `![TechnologyName](badge-url)` |
```

## Related Resources

- [Shields.io Documentation](https://shields.io/)
- [Simple Icons](https://simpleicons.org/)
- [GitHub README Stats](https://github.com/anuraghazra/github-readme-stats)
- [Markdown Badges Guide](https://github.com/Ileriayo/markdown-badges)

---

<div align="center">
  <p>Maintained by the DIO Community</p>
  <p><a href="../API_DOCUMENTATION.md">← Back to API Documentation</a></p>
</div>