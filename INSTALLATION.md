# JellyTV - Apple TV Custom CSS for Jellyfin

Transform your Jellyfin media server interface to look and feel like Apple TV with this comprehensive custom CSS theme.

## 🎨 Features

This custom CSS brings the following Apple TV design elements to Jellyfin:

- **San Francisco Font Family**: Uses Apple's system fonts for an authentic look
- **Dark, Minimalist Interface**: True black backgrounds with subtle gradients
- **Glassmorphism Effects**: Blur effects and translucent panels
- **Card-Based UI**: Rounded corners with elevation shadows
- **Smooth Animations**: Cubic-bezier transitions for fluid interactions
- **Focus States**: White glow effects for keyboard/remote navigation
- **Apple TV Color Palette**: Accurate colors matching tvOS
- **Responsive Design**: Optimized for desktop, tablet, and mobile
- **Enhanced Typography**: Apple's letter-spacing and font weights
- **Video Player OSD**: Styled playback controls matching Apple TV

## 📋 Requirements

- Jellyfin Server (10.7.0 or higher recommended)
- Modern web browser with CSS support:
  - Chrome/Edge 88+
  - Firefox 85+
  - Safari 14+
  - Mobile browsers (iOS Safari, Chrome Mobile)

## 🚀 Installation

### Method 1: Via Jellyfin Dashboard (Recommended)

1. **Open your Jellyfin server** in a web browser
2. **Log in** as an administrator
3. **Navigate to Dashboard**:
   - Click the hamburger menu (☰) in the top left
   - Select "Dashboard"
4. **Go to General Settings**:
   - In the left sidebar, click "General"
5. **Scroll down to Custom CSS**:
   - Find the "Custom CSS" section
6. **Copy and paste the CSS**:
   - Open `jellyfin-appletv.css` from this repository
   - Copy the entire contents
   - Paste into the Custom CSS text area in Jellyfin
7. **Save changes**:
   - Click "Save" at the bottom of the page
8. **Refresh your browser**:
   - Press `Ctrl+F5` (Windows/Linux) or `Cmd+Shift+R` (Mac)
   - The new theme should now be active!

### Method 2: Via Direct File Access

If you have access to the Jellyfin server files:

1. **Locate your Jellyfin data directory**:
   - Linux: `/var/lib/jellyfin/` or `/etc/jellyfin/`
   - Windows: `C:\ProgramData\Jellyfin\Server\`
   - Docker: Volume mounted to `/config`

2. **Navigate to the web config**:
   ```
   /path/to/jellyfin/config/
   ```

3. **Edit or create custom CSS file**:
   - Some Jellyfin installations allow CSS in: `config/branding.css`
   - Or configure via `config/system.xml` under `<CustomCss>` tag

4. **Restart Jellyfin server**

5. **Clear browser cache and reload**

## 🎯 What Gets Styled

This theme modifies the following Jellyfin interface elements based on **Apple's Human Interface Guidelines for tvOS**:

### Navigation & Layout (Apple's Top Bar Pattern)
- Header bar with glassmorphism (backdrop-filter: blur(40px))
- Sidebar navigation menu with focus states
- Breadcrumbs and page titles using SF Pro Display weights

### Content Cards (Apple's Lockup Pattern)
- Movie/TV show posters (2:3 aspect ratio)
- Episode thumbnails (16:9 aspect ratio)
- Library items with proper spacing
- Home screen recommendations
- **Focus States**: White glow + scale(1.08) + elevation

### Media Details Pages (Apple's Hero Layout)
- Backdrop images with gradient overlays
- Title and metadata display with SF typography
- Play and action buttons (iOS-style)
- Cast and crew information

### Video Player
- On-screen display (OSD)
- Playback controls
- Chapter thumbnails
- Subtitle styling

### Forms & Inputs
- Search bars
- Login forms
- Settings pages
- Input fields and dropdowns

### Modals & Dialogs
- Confirmation dialogs
- Context menus
- User menus
- Settings modals

## 🎨 Customization

You can customize the theme by modifying the CSS variables at the top of the file:

```css
:root {
    /* Adjust colors */
    --appletv-accent: #0a84ff;  /* Change primary accent color */
    
    /* Adjust spacing */
    --spacing-lg: 32px;  /* Increase/decrease spacing */
    
    /* Adjust effects */
    --glass-bg: rgba(28, 28, 30, 0.72);  /* Adjust transparency */
}
```

### Color Scheme Variants

To create a lighter variant, you could modify:
```css
--appletv-black: #1c1c1e;  /* Lighter background */
--appletv-gray: #2c2c2e;   /* Adjusted surfaces */
```

### Typography Adjustments

To adjust font sizes globally:
```css
/* Make everything slightly larger */
h1, .pageTitle { font-size: 52px !important; }
h2, .sectionTitle { font-size: 36px !important; }
body { font-size: 18px !important; }
```

## 🖥️ Browser Compatibility

| Browser | Support | Notes |
|---------|---------|-------|
| Chrome/Edge 88+ | ✅ Full | Best experience |
| Firefox 85+ | ✅ Full | Excellent support |
| Safari 14+ | ✅ Full | Native backdrop-filter |
| Opera 74+ | ✅ Full | Chromium-based |
| Mobile Safari | ✅ Full | iOS 14+ |
| Chrome Mobile | ✅ Full | Android 5+ |

**Note**: Older browsers may not support `backdrop-filter` for glassmorphism effects but will still display a usable dark theme.

## 📱 Remote Control & TV Support

This theme is optimized for:
- **Keyboard navigation**: Focus states with white glow
- **Remote controls**: Large touch targets
- **TV interfaces**: High contrast and readable text
- **Game controllers**: Proper focus management

The theme includes special `:focus` styles for navigation without a mouse.

## 🐛 Troubleshooting

### Theme not applying
1. Make sure you saved the settings in Dashboard
2. Hard refresh your browser (`Ctrl+F5` or `Cmd+Shift+R`)
3. Clear browser cache
4. Check browser console for CSS errors

### Fonts look different
- The theme uses system fonts that fallback gracefully
- On non-Apple devices, you'll see similar fonts (Inter, Segoe UI, Roboto)
- For true San Francisco fonts, use Safari on macOS/iOS

### Elements look broken
1. Ensure you're using a modern browser (see compatibility table)
2. Some custom Jellyfin plugins may conflict with CSS
3. Try disabling other custom CSS temporarily

### Performance issues
- Glassmorphism effects (`backdrop-filter`) can impact performance on older devices
- Consider disabling blur effects if needed:
  ```css
  backdrop-filter: none !important;
  -webkit-backdrop-filter: none !important;
  ```

### Mobile layout issues
- The theme is responsive but some Jellyfin mobile layouts may vary
- Report specific issues with device/browser information

## 🔄 Updates

To update the theme:
1. Download the latest `jellyfin-appletv.css`
2. Copy the entire contents
3. Replace the existing CSS in your Jellyfin Dashboard > General > Custom CSS
4. Save and refresh your browser

## 🤝 Contributing

Found an issue or want to improve the theme?

1. **Report Issues**: Open an issue with:
   - Browser version
   - Jellyfin version
   - Screenshot of the problem
   - Specific page/element affected

2. **Suggest Improvements**: 
   - CSS optimizations
   - New Apple TV features to mimic
   - Accessibility enhancements

## 📄 License

This custom CSS is provided as-is for use with Jellyfin. Feel free to modify and distribute.

## 🙏 Credits

- **Apple**: Design inspiration from tvOS and Apple TV interface
- **Jellyfin**: The amazing open-source media server
- **Community**: Various CSS techniques and improvements

## 📸 Screenshots

(Screenshots would show here in a complete installation)

### Home Screen
- Apple TV-style card layout
- Glassmorphism header
- Smooth hover effects

### Detail Pages
- Backdrop with gradient overlay
- San Francisco typography
- Apple TV-style buttons

### Video Player
- Clean OSD design
- Apple TV-inspired controls
- Chapter thumbnails

## ⚙️ Advanced Configuration

### Jellyfin Server Configuration

For optimal performance, consider these Jellyfin settings:

1. **Dashboard > Playback**:
   - Enable hardware acceleration if available
   - Optimize streaming settings

2. **Dashboard > Users**:
   - Set appropriate permissions
   - Configure display preferences

3. **Dashboard > Libraries**:
   - Ensure metadata is properly fetched
   - Use high-quality artwork for best appearance

### Web Client Settings

Within Jellyfin's web client:

1. **Display Settings**:
   - Enable "Prefer fMP4-HLS Media Container"
   - Set video quality preferences

2. **Home Screen**:
   - Customize what sections appear
   - Arrange in preferred order

## 🎬 Best Practices

For the best Apple TV-like experience:

1. **Use High-Quality Artwork**:
   - Let Jellyfin fetch metadata from TMDB/TVDB
   - High-resolution posters and backdrops look best

2. **Organize Your Library**:
   - Proper naming conventions
   - Complete metadata
   - Season/episode organization

3. **Enable Collections**:
   - Group movie franchises
   - Create custom collections
   - Better browsing experience

4. **Configure Continue Watching**:
   - Prominent on home screen
   - Apple TV-style resume functionality

## 🆘 Support

For help and support:

1. **Jellyfin Documentation**: [jellyfin.org/docs](https://jellyfin.org/docs/)
2. **Jellyfin Forums**: Community support for CSS customization
3. **Repository Issues**: Report bugs or request features

## 🔮 Future Enhancements

Potential improvements for future versions:

- [ ] Dynamic color themes based on content
- [ ] Seasonal themes (holiday variants)
- [ ] Enhanced animations
- [ ] Better mobile/tablet optimization
- [ ] Additional language support
- [ ] Theme variants (light mode, color schemes)
- [ ] Integration with Jellyfin plugins

---

**Enjoy your Apple TV-style Jellyfin experience! 🎉**
