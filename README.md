# S1 Dedicated Servers Wiki

A comprehensive and beautifully designed wiki for Schedule One dedicated servers, built with MkDocs Material theme.

## Features

### 🎨 **Enhanced Visual Design**
- **Dual Theme Support**: Light and dark mode with smooth transitions
- **Custom Color Scheme**: Indigo-based color palette with gradients
- **Modern Typography**: Roboto fonts for optimal readability
- **Responsive Design**: Mobile-friendly layout with adaptive components

### 🚀 **Interactive Elements**
- **Copy Code Buttons**: One-click code copying with visual feedback
- **Reading Progress Bar**: Shows reading progress at the top of the page
- **Back to Top Button**: Smooth scrolling back to the top
- **Smooth Scrolling**: Enhanced navigation experience
- **Table of Contents Highlighting**: Active section highlighting

### 🔍 **Enhanced Search & Navigation**
- **Advanced Search**: Highlighted search results and suggestions
- **Keyboard Shortcuts**: 
  - `Ctrl/Cmd + K`: Focus search
  - `Escape`: Close search
- **Navigation Tabs**: Organized content sections
- **Breadcrumb Navigation**: Easy page navigation

### 📱 **User Experience Improvements**
- **Loading Animations**: Smooth image loading transitions
- **Tooltips**: Enhanced information display
- **Custom Scrollbars**: Styled scrollbars for better aesthetics
- **Hover Effects**: Interactive element feedback

## Installation

1. **Install Python Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Install MkDocs**:
   ```bash
   pip install mkdocs
   ```

3. **Install Material Theme**:
   ```bash
   pip install mkdocs-material
   ```

## Usage

### **Local Development**:
```bash
# Start local development server
mkdocs serve

# Build the site
mkdocs build
```

### **Deployment**:
```bash
# Deploy to GitHub Pages
mkdocs gh-deploy
```

## Configuration

The wiki is configured through `mkdocs.yml` with the following key features:

- **Material Theme**: Modern, responsive design
- **Dual Color Schemes**: Light and dark mode support
- **Enhanced Navigation**: Tabs, sections, and expandable navigation
- **Search Features**: Highlighting, sharing, and suggestions
- **Code Features**: Copy buttons, annotations, and syntax highlighting
- **Markdown Extensions**: Admonitions, tabs, task lists, and more

## Customization

### **Colors**:
Edit `stylesheets/extra.css` to modify the color scheme:
```css
:root {
  --s1-primary: #3f51b5;    /* Primary color */
  --s1-accent: #2196f3;     /* Accent color */
  --s1-secondary: #ff9800;   /* Secondary color */
}
```

### **Features**:
Modify `mkdocs.yml` to enable/disable specific features:
```yaml
theme:
  features:
    - navigation.tabs
    - search.highlight
    - content.code.copy
```

### **JavaScript**:
Edit `javascripts/extra.js` to add custom functionality or modify existing features.

## File Structure

```
S1DedicatedServersWiki/
├── mkdocs.yml              # Main configuration
├── requirements.txt         # Python dependencies
├── README.md               # This file
├── stylesheets/
│   └── extra.css          # Custom CSS styles
├── javascripts/
│   └── extra.js           # Custom JavaScript
├── docs/                  # Documentation files
│   ├── index.md
│   ├── configuration.md
│   ├── commands.md
│   └── troubleshooting.md
└── assets/                # Images and media
    ├── logo.png
    └── favicon.png
```

## Browser Support

- **Modern Browsers**: Chrome 80+, Firefox 75+, Safari 13+, Edge 80+
- **Mobile**: iOS Safari 13+, Chrome Mobile 80+
- **Features**: CSS Grid, Flexbox, ES6+ JavaScript

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally with `mkdocs serve`
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions:
- **GitHub Issues**: [Create an issue](https://github.com/ifbars/S1DedicatedServersWiki/issues)
- **Discord**: [Join our community](https://discord.gg/scheduleone)

---

Built with ❤️ by the Schedule One community
