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

### Method 1: Using CDN (Recommended - Easy Updates)

**Paste the following in Custom CSS code box:**

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");
```

**Detailed steps:**

1. Open **Dashboard** from Administration tab in Settings
2. From the sidebar, select the **General** tab (or **Branding** tab on Jellyfin 10.11.X+)
3. Scroll down to find **Custom CSS** code box
4. Paste the import code above in the Custom CSS box
5. Click **Save**
6. **Hard refresh** your browser (`Ctrl+F5` on Windows/Linux or `Cmd+Shift+R` on Mac)

### Method 2: Direct Copy-Paste

1. **Copy the CSS**:
   - Open [jellyfin-appletv.css](jellyfin-appletv.css) from this repository
   - Copy the entire contents

2. **Install in Jellyfin**:
   - Open Jellyfin Dashboard
   - Navigate to **General** settings (or **Branding** on 10.11.X+)
   - Scroll to **Custom CSS** section
   - Paste the entire CSS content
   - Click **Save**

3. **Refresh your browser** (`Ctrl+F5` or `Cmd+Shift+R`)

For more installation options and detailed instructions, see [INSTALLATION.md](INSTALLATION.md).

> **Note**: The CDN method (Method 1) is recommended as you'll automatically receive theme updates when refreshing. The direct copy-paste method requires manually updating the CSS when new versions are released.

## 📋 Requirements

- **Jellyfin Server**: 10.7.0 or higher
- **Browser**: Modern browser with CSS3 support
  - Chrome/Edge 88+
  - Firefox 85+
  - Safari 14+
  - Mobile browsers (iOS/Android)

## 📁 Files

- **`jellyfin-appletv.css`** - The main custom CSS theme file
- **`README.md`** - This file - Quick start and overview
- **`INSTALLATION.md`** - Detailed installation guide with multiple methods
- **`DESIGN-PRINCIPLES.md`** - Apple's Human Interface Guidelines implementation
- **`PREVIEW.md`** - Visual examples and interface walkthroughs

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

## 🖼️ Preview & Screenshots

> **Want to see what it looks like?** Check out [PREVIEW.md](PREVIEW.md) for detailed visual examples and interface walkthroughs.

After installation, the interface will feature:
- **Clean, card-based layout** with Apple TV-style design
- **Dark backgrounds** with subtle gradients (true black #000000)
- **Smooth hover and focus effects** (scale 1.08 + white glow)
- **Glassmorphic headers and menus** with backdrop blur
- **Apple TV-style typography** (San Francisco fonts or system equivalents)
- **Generous spacing** optimized for comfortable viewing
- **Remote/keyboard friendly** with clear focus states

## 🎨 Customization

The theme uses CSS variables for easy customization. You can override these by adding custom CSS **after** the import statement.

### Available Customization Options

#### 1. Change Accent Color

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");

:root {
    --appletv-accent: #ff2d55;      /* Change to pink accent */
    --appletv-accent-hover: #ff375f;
}
```

#### 2. Adjust Card Hover Effects

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");

/* Increase hover scale */
.card:hover,
.cardBox:hover,
.itemTile:hover {
    transform: scale(1.12) translateY(-12px) !important;
}
```

#### 3. Customize Glassmorphism Intensity

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");

:root {
    --glass-bg: rgba(28, 28, 30, 0.9);  /* More opaque */
}

/* Or disable blur effects for better performance */
.skinHeader,
.headerTop,
.mainDrawer,
.dialog {
    backdrop-filter: none !important;
    -webkit-backdrop-filter: none !important;
}
```

#### 4. Adjust Spacing

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");

:root {
    --spacing-lg: 40px;    /* Increase spacing */
    --spacing-xl: 60px;    /* Increase spacing */
}
```

#### 5. Modify Border Radius

```css
@import url("https://cdn.jsdelivr.net/gh/aditya-damerla128/jellytv@main/jellyfin-appletv.css");

:root {
    --radius-lg: 20px;     /* More rounded corners */
    --radius-xl: 24px;
}
```

### All Available CSS Variables

```css
:root {
    /* Colors */
    --appletv-black: #000000;
    --appletv-dark-gray: #0a0a0a;
    --appletv-gray: #1c1c1e;
    --appletv-light-gray: #2c2c2e;
    --appletv-lighter-gray: #3a3a3c;
    --appletv-white: #ffffff;
    --appletv-focus: rgba(255, 255, 255, 0.15);
    --appletv-accent: #0a84ff;
    --appletv-accent-hover: #409cff;
    
    /* Glassmorphism */
    --glass-bg: rgba(28, 28, 30, 0.72);
    --glass-border: rgba(255, 255, 255, 0.1);
    
    /* Spacing */
    --spacing-xs: 8px;
    --spacing-sm: 12px;
    --spacing-md: 20px;
    --spacing-lg: 32px;
    --spacing-xl: 48px;
    
    /* Border Radius */
    --radius-sm: 8px;
    --radius-md: 12px;
    --radius-lg: 16px;
    --radius-xl: 20px;
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

- **[INSTALLATION.md](INSTALLATION.md)** - Complete installation guide with multiple methods
- **[DESIGN-PRINCIPLES.md](DESIGN-PRINCIPLES.md)** - Apple's Human Interface Guidelines implementation
- **[Jellyfin Documentation](https://jellyfin.org/docs/)** - Official Jellyfin docs
- **[Jellyfin Custom CSS Guide](https://jellyfin.org/docs/general/clients/css-customization.html)** - CSS customization reference

### Apple Design References

This theme is based on Apple's official design guidelines:
- **[Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines)** - Core design principles
- **[tvOS Guidelines](https://developer.apple.com/design/human-interface-guidelines/tvos)** - Platform-specific patterns
- **[Designing for tvOS](https://developer.apple.com/design/human-interface-guidelines/designing-for-tvos)** - Detailed tvOS design guide
- **[Design Resources](https://developer.apple.com/design/resources/)** - Download SF fonts, UI kits, and templates

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

This custom CSS follows both Jellyfin's and Apple's official guidelines:

### Jellyfin CSS Guidelines
- Uses standard CSS selectors for Jellyfin elements
- Maintains responsive design principles
- Preserves accessibility features
- Compatible with Jellyfin's web client architecture
- Follows CSS best practices with proper specificity

Reference: [Jellyfin CSS Customization Guide](https://jellyfin.org/docs/general/clients/css-customization.html)

### Apple Human Interface Guidelines
- Implements Apple's three core principles: **Clarity, Deference, and Depth**
- Follows tvOS-specific patterns (Focus Engine, layering, card design)
- Uses San Francisco font family (system fonts with graceful fallbacks)
- Applies official Apple color palette and spacing scales
- Implements glassmorphism (backdrop blur) as seen in modern Apple interfaces
- Optimized for 10-foot viewing distance (living room context)

References:
- [Apple HIG](https://developer.apple.com/design/human-interface-guidelines)
- [tvOS Design Guidelines](https://developer.apple.com/design/human-interface-guidelines/tvos)
- [Designing for tvOS](https://developer.apple.com/design/human-interface-guidelines/designing-for-tvos)
- [Apple Design Resources](https://developer.apple.com/design/resources/)

For detailed implementation of Apple's design principles, see [DESIGN-PRINCIPLES.md](DESIGN-PRINCIPLES.md).

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
