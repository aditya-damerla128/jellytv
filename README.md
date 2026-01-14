# JellyTV 🎬

A custom Jellyfin CSS theme that transforms your media server interface to perfectly mimic the Apple TV (tvOS) experience.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Jellyfin](https://img.shields.io/badge/Jellyfin-10.7%2B-purple.svg)
![CSS](https://img.shields.io/badge/CSS-Custom-green.svg)

## ✨ Overview

JellyTV brings the sleek, minimalist design of Apple TV to your Jellyfin media server. Experience the same beautiful interface, smooth animations, and thoughtful design details that make Apple TV a pleasure to use.

## 🎯 Key Features

- 🍎 **Authentic Apple TV Design** - Pixel-perfect recreation of tvOS interface
- 🔤 **San Francisco Typography** - Apple's signature font family (with system fallbacks)
- 🌈 **Glassmorphism Effects** - Beautiful blur and transparency effects
- 🎨 **Dark Theme** - True black backgrounds with subtle gradients
- ✨ **Smooth Animations** - Fluid transitions using cubic-bezier curves
- 🎮 **Remote Control Ready** - Optimized for keyboard/remote navigation
- 📱 **Fully Responsive** - Works on desktop, tablet, and mobile
- ♿ **Accessible** - High contrast and focus states for better usability

## 🚀 Quick Start

1. **Copy the CSS**:
   ```bash
   # View the CSS file
   cat jellyfin-appletv.css
   ```

2. **Install in Jellyfin**:
   - Open Jellyfin Dashboard
   - Navigate to **General** settings
   - Scroll to **Custom CSS** section
   - Paste the entire CSS content
   - Click **Save**

3. **Refresh your browser** (`Ctrl+F5` or `Cmd+Shift+R`)

For detailed installation instructions, see [INSTALLATION.md](INSTALLATION.md).

## 📋 Requirements

- **Jellyfin Server**: 10.7.0 or higher
- **Browser**: Modern browser with CSS3 support
  - Chrome/Edge 88+
  - Firefox 85+
  - Safari 14+
  - Mobile browsers (iOS/Android)

## 📁 Files

- `jellyfin-appletv.css` - The main custom CSS theme
- `INSTALLATION.md` - Detailed installation and configuration guide
- `README.md` - This file

## 🎨 What's Included

This theme styles every aspect of the Jellyfin interface:

### Interface Elements
- ✅ Navigation header with glassmorphism
- ✅ Sidebar menu with hover effects
- ✅ Media cards with smooth transitions
- ✅ Detail pages with backdrop gradients
- ✅ Video player OSD
- ✅ Forms and input fields
- ✅ Modals and dialogs
- ✅ Context menus
- ✅ Search interface
- ✅ Settings pages

### Design Details
- ✅ Apple TV color palette
- ✅ Rounded corners (8px, 12px, 16px, 20px)
- ✅ Card shadows and elevation
- ✅ Focus states with white glow
- ✅ Progress bars and indicators
- ✅ Custom scrollbars
- ✅ Toast notifications
- ✅ Loading states

## 🖼️ Screenshots

> **Note**: After installation, the interface will feature:
> - Clean, card-based layout
> - Dark backgrounds with subtle gradients
> - Smooth hover and focus effects
> - Glassmorphic headers and menus
> - Apple TV-style typography

## 🎨 Customization

The theme uses CSS variables for easy customization. Modify these at the top of the CSS file:

```css
:root {
    /* Colors */
    --appletv-accent: #0a84ff;      /* Primary blue accent */
    --appletv-black: #000000;       /* True black background */
    
    /* Spacing */
    --spacing-lg: 32px;             /* Large spacing */
    --spacing-xl: 48px;             /* Extra large spacing */
    
    /* Border Radius */
    --radius-lg: 16px;              /* Card corners */
    
    /* Effects */
    --glass-bg: rgba(28, 28, 30, 0.72);  /* Glassmorphism */
}
```

## 🔧 Configuration

### Jellyfin Settings for Best Experience

1. **Enable Hardware Acceleration** (Dashboard > Playback)
2. **Fetch High-Quality Artwork** (Dashboard > Libraries)
3. **Organize Media Properly** (correct naming conventions)
4. **Enable Collections** (group movie franchises)

### Browser Recommendations

- **Best**: Safari on macOS/iOS (native San Francisco fonts)
- **Great**: Chrome/Edge (excellent CSS support)
- **Good**: Firefox (full feature support)

## 🐛 Troubleshooting

**Theme not appearing?**
- Hard refresh: `Ctrl+F5` (Windows/Linux) or `Cmd+Shift+R` (Mac)
- Clear browser cache
- Verify CSS was saved in Jellyfin Dashboard

**Fonts look different?**
- Non-Apple devices use fallback fonts (Inter, Segoe UI, Roboto)
- This is expected and maintains readability

**Performance issues?**
- Glassmorphism can impact older devices
- Consider disabling `backdrop-filter` if needed

See [INSTALLATION.md](INSTALLATION.md) for more troubleshooting tips.

## 📖 Documentation

- **[INSTALLATION.md](INSTALLATION.md)** - Complete installation guide
- **[Jellyfin Documentation](https://jellyfin.org/docs/)** - Official Jellyfin docs
- **[Jellyfin Custom CSS Guide](https://jellyfin.org/docs/general/clients/css-customization.html)** - CSS customization reference

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Report Issues**: Found a bug? Open an issue with:
   - Browser and version
   - Jellyfin version
   - Screenshot of the problem
   - Steps to reproduce

2. **Suggest Features**: Have ideas for improvements?
   - New Apple TV features to implement
   - Performance optimizations
   - Accessibility enhancements

3. **Submit Pull Requests**: Want to contribute code?
   - Fork the repository
   - Make your changes
   - Test thoroughly
   - Submit a PR with description

## 📜 Based on Jellyfin Guidelines

This custom CSS follows Jellyfin's official guidelines for CSS customization:

- Uses standard CSS selectors for Jellyfin elements
- Maintains responsive design principles
- Preserves accessibility features
- Compatible with Jellyfin's web client architecture
- Follows CSS best practices with proper specificity

Reference: [Jellyfin CSS Customization Guide](https://jellyfin.org/docs/general/clients/css-customization.html)

## 🎯 Design Philosophy

JellyTV adheres to Apple's design principles:

1. **Clarity**: Typography and layout focus on content
2. **Deference**: UI elements don't compete with content
3. **Depth**: Layers and motion convey hierarchy
4. **Simplicity**: Refined, uncluttered interface
5. **Consistency**: Predictable, familiar interactions

## 🔮 Roadmap

Future enhancements planned:

- [ ] Light mode variant (Apple TV light theme)
- [ ] Seasonal themes (holiday variants)
- [ ] Dynamic accent colors based on content
- [ ] Enhanced mobile optimizations
- [ ] More animation refinements
- [ ] Integration with Jellyfin plugins
- [ ] Theme configuration UI

## 📄 License

This project is open source and available for anyone to use, modify, and distribute.

## 🙏 Acknowledgments

- **Apple** - Design inspiration from tvOS and Apple TV
- **Jellyfin Team** - Amazing open-source media server platform
- **Community** - CSS techniques and feedback

## 💬 Support

Need help or have questions?

- **Issues**: Open an issue on GitHub
- **Jellyfin Forums**: Community support
- **Documentation**: See INSTALLATION.md

## ⭐ Show Your Support

If you like JellyTV, please:
- ⭐ Star this repository
- 🐛 Report bugs or suggest features
- 📢 Share with others
- 🤝 Contribute improvements

---

**Transform your Jellyfin into Apple TV today! 🍎✨**
