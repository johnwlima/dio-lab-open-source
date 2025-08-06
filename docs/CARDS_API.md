# GitHub Cards API Documentation

<div align="center">
  <img src="https://img.shields.io/badge/GitHub-Cards-E94D5F?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Cards API">
  <h1>GitHub Stats Cards API</h1>
  <p>Dynamic GitHub statistics and profile enhancement cards</p>
</div>

## Overview

The GitHub Cards API provides dynamic, customizable cards for displaying GitHub statistics, repository information, and contribution data. These cards are perfect for enhancing README profiles with real-time data visualization.

**Sources:**
- [`utils/cards/github-stats.md`](../utils/cards/github-stats.md)
- [`utils/cards/github-streak-stats.md`](../utils/cards/github-streak-stats.md)

**Powered by:**
- [GitHub README Stats](https://github.com/anuraghazra/github-readme-stats) by @anuraghazra
- [GitHub Streak Stats](https://github.com/denvercoder1/github-readme-streak-stats) by @DenverCoder1

## Quick Start

```markdown
<!-- Basic GitHub stats -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true)

<!-- Language stats -->
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact)

<!-- Streak stats -->
[![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername)](https://git.io/streak-stats)
```

## Card Types

### 1. GitHub Statistics Card

Display comprehensive GitHub account statistics including commits, PRs, issues, and stars.

#### Basic Usage

```markdown
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&theme=transparent&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)
```

#### DIO Theme Configuration

| Parameter | Value | Description |
|-----------|--------|-------------|
| `theme` | `transparent` | Transparent background theme |
| `bg_color` | `000` | Black background |
| `border_color` | `30A3DC` | DIO blue border |
| `show_icons` | `true` | Display category icons |
| `icon_color` | `30A3DC` | DIO blue icons |
| `title_color` | `E94D5F` | DIO red title |
| `text_color` | `FFF` | White text |

#### Preview

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=SEUUSERNAME&theme=transparent&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)

### 2. Most Used Languages Card

Visualize your programming language distribution across repositories.

#### Standard Layout

```markdown
![Top Languages](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=yourusername&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)
```

#### Compact Layout

```markdown
![Top Languages](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=yourusername&layout=compact&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)
```

#### Configuration Options

| Parameter | Options | Description |
|-----------|---------|-------------|
| `layout` | `default`, `compact` | Card layout style |
| `langs_count` | `1-10` | Number of languages to display |
| `exclude_repo` | `repo1,repo2` | Repositories to exclude |
| `hide` | `lang1,lang2` | Languages to hide |
| `card_width` | `number` | Custom card width |

#### Previews

**Standard Layout:**
![Most Used Languages](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=elidianaandrade&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)

**Compact Layout:**
![Most Used Languages](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=elidianaandrade&layout=compact&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)

### 3. Repository Pin Card

Showcase specific repositories with detailed information.

#### Usage

```markdown
[![Repository Card](https://github-readme-stats.vercel.app/api/pin/?username=yourusername&repo=yourrepository&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/yourusername/yourrepository)
```

#### Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `username` | GitHub username | `yourusername` |
| `repo` | Repository name | `awesome-project` |
| `show_owner` | Show repository owner | `true`, `false` |
| `description_lines_count` | Description line limit | `1-3` |

#### Preview

[![Repository Card](https://github-readme-stats.vercel.app/api/pin/?username=digitalinnovationone&repo=roadmaps&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/digitalinnovationone/roadmaps)

### 4. GitHub Streak Stats Card

Track consecutive contribution days and longest streaks.

#### Basic Usage

```markdown
[![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername&theme=bear&background=000&border=30A3DC&dates=FFF)](https://git.io/streak-stats)
```

#### DIO Theme Configuration

| Parameter | Value | Description |
|-----------|--------|-------------|
| `theme` | `bear` | Base theme |
| `background` | `000` | Black background |
| `border` | `30A3DC` | DIO blue border |
| `dates` | `FFF` | White date text |
| `ring` | `30A3DC` | DIO blue accent ring |
| `fire` | `E94D5F` | DIO red streak fire |
| `currStreakLabel` | `FFF` | Current streak label color |
| `sideLabels` | `FFF` | Side label colors |
| `currStreakNum` | `FFF` | Current streak number color |

#### Advanced Customization

```markdown
[![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername&theme=bear&background=000&border=30A3DC&dates=FFF&ring=30A3DC&fire=E94D5F&currStreakLabel=FFF&sideLabels=FFF&currStreakNum=FFF)](https://git.io/streak-stats)
```

#### Preview

[![GitHub Streak](https://streak-stats.demolab.com/?user=elidianaandrade&theme=bear&background=000&border=30A3DC&dates=FFF)](https://git.io/streak-stats)

## Advanced Configuration

### Color Customization

#### DIO Brand Colors

```markdown
<!-- Official DIO Color Palette -->
Primary Blue: 30A3DC
Secondary Red: E94D5F
Background: 000000 (Black)
Text: FFFFFF (White)
Border: 30A3DC
Accents: E94D5F
```

#### Custom Color Examples

```markdown
<!-- Dark theme with purple accents -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&bg_color=0d1117&border_color=6e40c9&title_color=6e40c9&text_color=ffffff&icon_color=6e40c9)

<!-- Light theme with blue accents -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&bg_color=ffffff&border_color=30a3dc&title_color=30a3dc&text_color=333333&icon_color=30a3dc)

<!-- Gradient background -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&bg_color=30,e94d5f,30a3dc&title_color=fff&text_color=fff&icon_color=fff)
```

### Privacy and Security

#### Hiding Sensitive Information

```markdown
<!-- Hide specific statistics -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&hide=issues,contribs,prs&show_icons=true)

<!-- Hide private repository contributions -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&count_private=false)

<!-- Exclude specific repositories from language stats -->
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&exclude_repo=private-repo,secret-project)
```

#### Available Hide Options

| Option | Description |
|--------|-------------|
| `stars` | Total stars received |
| `commits` | Total commits |
| `prs` | Pull requests opened |
| `issues` | Issues opened |
| `contribs` | Total contributions |
| `rank` | User rank |

### Performance Optimization

#### Caching Strategy

```markdown
<!-- Cards are cached for 4 hours by default -->
<!-- Force refresh by changing any parameter -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&v=1)

<!-- Custom cache busting -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&cache_seconds=1800)
```

#### Size Optimization

```markdown
<!-- Compact layouts for better performance -->
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact&langs_count=6)

<!-- Disable icons for faster loading -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=false)
```

## Complete Implementation Examples

### Professional Profile Layout

```markdown
<div align="center">

## 📊 GitHub Statistics

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&theme=transparent&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)

![Top Languages](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=yourusername&layout=compact&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF)

[![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername&theme=bear&background=000&border=30A3DC&dates=FFF)](https://git.io/streak-stats)

</div>
```

### Side-by-Side Layout

```markdown
<div align="center">
  
  <!-- GitHub Stats and Languages side by side -->
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true&theme=transparent&bg_color=000&border_color=30A3DC&icon_color=30A3DC&title_color=E94D5F&text_color=FFF"/>
  <img height="180em" src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=yourusername&layout=compact&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF"/>
  
</div>

<div align="center">
  
  <!-- Streak stats below -->
  [![GitHub Streak](https://streak-stats.demolab.com/?user=yourusername&theme=bear&background=000&border=30A3DC&dates=FFF)](https://git.io/streak-stats)
  
</div>
```

### Repository Showcase

```markdown
## 🏆 Featured Projects

<div align="center">

[![Project 1](https://github-readme-stats.vercel.app/api/pin/?username=yourusername&repo=project1&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/yourusername/project1)

[![Project 2](https://github-readme-stats.vercel.app/api/pin/?username=yourusername&repo=project2&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/yourusername/project2)

</div>
```

## API Functions & Integrations

### JavaScript Integration

```javascript
// Generate GitHub stats card URL
function generateGitHubStatsUrl(username, options = {}) {
  const baseUrl = 'https://github-readme-stats.vercel.app/api';
  const defaultOptions = {
    theme: 'transparent',
    bg_color: '000',
    border_color: '30A3DC',
    show_icons: 'true',
    icon_color: '30A3DC',
    title_color: 'E94D5F',
    text_color: 'FFF'
  };
  
  const params = new URLSearchParams({ 
    username, 
    ...defaultOptions, 
    ...options 
  });
  
  return `${baseUrl}?${params.toString()}`;
}

// Usage
const statsUrl = generateGitHubStatsUrl('yourusername', {
  hide: 'issues,contribs',
  count_private: 'true'
});

console.log(statsUrl);
```

### Dynamic Card Generation

```javascript
// React component for GitHub cards
function GitHubStatsCard({ username, cardType = 'stats', ...props }) {
  const cardUrls = {
    stats: `https://github-readme-stats.vercel.app/api?username=${username}`,
    languages: `https://github-readme-stats.vercel.app/api/top-langs/?username=${username}`,
    streak: `https://streak-stats.demolab.com/?user=${username}`
  };
  
  const params = new URLSearchParams({
    theme: 'transparent',
    bg_color: '000',
    border_color: '30A3DC',
    title_color: 'E94D5F',
    text_color: 'FFF',
    ...props
  });
  
  const url = `${cardUrls[cardType]}&${params.toString()}`;
  
  return (
    <img 
      src={url} 
      alt={`${username} GitHub ${cardType}`}
      loading="lazy"
    />
  );
}

// Usage
<GitHubStatsCard 
  username="yourusername" 
  cardType="stats" 
  show_icons="true"
  icon_color="30A3DC"
/>
```

### Card Validation

```javascript
// Validate GitHub username for card generation
async function validateGitHubUsername(username) {
  try {
    const response = await fetch(`https://api.github.com/users/${username}`);
    return response.ok;
  } catch (error) {
    console.error('Username validation failed:', error);
    return false;
  }
}

// Check card availability
async function checkCardAvailability(cardUrl) {
  try {
    const response = await fetch(cardUrl, { method: 'HEAD' });
    return response.ok;
  } catch (error) {
    console.error('Card availability check failed:', error);
    return false;
  }
}
```

## Troubleshooting

### Common Issues

#### 1. Cards Not Loading

**Symptoms:** Cards show as broken images or loading errors

**Solutions:**
```markdown
<!-- Check username spelling -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=correctusername)

<!-- Verify service availability -->
<!-- Try alternative endpoints -->
![GitHub Stats](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api?username=yourusername)
```

#### 2. Rate Limiting

**Symptoms:** Cards intermittently fail to load

**Solutions:**
```markdown
<!-- Use different service endpoints -->
<!-- Primary endpoint -->
![Stats](https://github-readme-stats.vercel.app/api?username=yourusername)

<!-- Alternative endpoint -->
![Stats](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api?username=yourusername)

<!-- Add cache busting for testing -->
![Stats](https://github-readme-stats.vercel.app/api?username=yourusername&v=2)
```

#### 3. Theme Inconsistencies

**Symptoms:** Colors don't match expected theme

**Solutions:**
```markdown
<!-- Explicitly set all color parameters -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&bg_color=000&border_color=30A3DC&title_color=E94D5F&text_color=FFF&icon_color=30A3DC)

<!-- Avoid conflicting theme and color parameters -->
<!-- Don't use theme with custom colors -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&bg_color=000&title_color=E94D5F)
```

### Debug Tools

```bash
# Test card URLs
curl -I "https://github-readme-stats.vercel.app/api?username=yourusername"

# Check GitHub API rate limits
curl -H "Accept: application/vnd.github.v3+json" https://api.github.com/rate_limit

# Validate username exists
curl -H "Accept: application/vnd.github.v3+json" https://api.github.com/users/yourusername
```

### Performance Monitoring

```javascript
// Monitor card load times
function monitorCardPerformance(cardUrl, cardName) {
  const startTime = performance.now();
  const img = new Image();
  
  img.onload = () => {
    const loadTime = performance.now() - startTime;
    console.log(`${cardName} loaded in ${loadTime.toFixed(2)}ms`);
  };
  
  img.onerror = () => {
    console.error(`${cardName} failed to load`);
  };
  
  img.src = cardUrl;
}

// Usage
monitorCardPerformance(
  'https://github-readme-stats.vercel.app/api?username=yourusername',
  'GitHub Stats Card'
);
```

## Best Practices

### 1. Consistent Branding

- Use DIO color scheme across all cards
- Maintain consistent styling parameters
- Align cards properly in layouts

### 2. Performance Optimization

- Use compact layouts when appropriate
- Limit the number of cards per page
- Implement lazy loading for multiple cards

### 3. Accessibility

- Provide meaningful alt text for all cards
- Ensure sufficient color contrast
- Test with screen readers

### 4. Responsive Design

```markdown
<!-- Mobile-friendly card sizes -->
<div align="center">
  <img width="49%" src="stats-card-url" />
  <img width="49%" src="languages-card-url" />
</div>

<!-- Stack on small screens -->
<div align="center">
  <img src="stats-card-url" style="max-width: 100%;" />
  <img src="languages-card-url" style="max-width: 100%;" />
</div>
```

### 5. Privacy Considerations

- Review what information cards expose
- Use privacy settings appropriately
- Consider excluding sensitive repositories

## Related Resources

- [GitHub README Stats Documentation](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Streak Stats Documentation](https://github.com/denvercoder1/github-readme-streak-stats)
- [Available Themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md)
- [Streak Stats Themes](https://github.com/DenverCoder1/github-readme-streak-stats/blob/main/docs/themes.md)
- [Simple Icons](https://simpleicons.org/)

## Contributing

Help improve the cards API documentation:

1. Test new card configurations
2. Report issues with specific parameters
3. Suggest new customization options
4. Contribute theme variations
5. Update examples with latest features

---

<div align="center">
  <p>Maintained by the DIO Community</p>
  <p><a href="../API_DOCUMENTATION.md">← Back to API Documentation</a></p>
</div>