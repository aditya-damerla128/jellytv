# Apple TV Design Principles

This document outlines how JellyTV implements Apple's Human Interface Guidelines for tvOS.

## Reference

Based on Apple's official Human Interface Guidelines:
- **Main Guide**: https://developer.apple.com/design/human-interface-guidelines
- **tvOS Guidelines**: https://developer.apple.com/design/human-interface-guidelines/tvos
- **Designing for tvOS**: https://developer.apple.com/design/human-interface-guidelines/designing-for-tvos
- **Design Resources**: https://developer.apple.com/design/resources/
- **tvOS UI Kit**: Download official design templates from Apple's design resources

## tvOS Design Overview

Apple TV is designed for **viewing from ~8-10 feet away** on large displays (typically 40-75 inches). This requires:

1. **Larger UI Elements**: Everything must be readable from across the room
2. **Focus-Driven Navigation**: The Siri Remote uses directional controls
3. **Cinematic Experience**: Content takes center stage with minimal UI
4. **Living Room Context**: Designed for relaxed, lean-back viewing
5. **High-Quality Visuals**: 4K HDR content with proper color grading

## Core Design Principles

### 1. Clarity

**Apple's Principle**: Text is legible at every size, icons are precise and lucid, adornments are subtle and appropriate, and a sharpened focus on functionality motivates the design.

**JellyTV Implementation**:
- **Typography**: San Francisco font family (Apple's system font) with proper weights
- **Font Sizes**: Large, readable text (h1: 48px, h2: 32px, body: 17px)
- **Letter Spacing**: Negative letter spacing (-0.02em to -0.01em) for better readability
- **Text Rendering**: `-webkit-font-smoothing: antialiased` for crisp text
- **High Contrast**: White text on dark backgrounds with minimum 7:1 contrast ratio
- **Icon Clarity**: Material Icons with proper sizing and weights

```css
/* Clarity Implementation */
body {
    font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text";
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-rendering: optimizeLegibility;
}

h1, .pageTitle {
    font-size: 48px;
    font-weight: 800;
    letter-spacing: -0.02em;
}
```

### 2. Deference

**Apple's Principle**: Fluid motion and a crisp, beautiful interface help people understand and interact with content while never competing with it.

**JellyTV Implementation**:
- **Dark Backgrounds**: True black (#000000) that doesn't compete with content
- **Glassmorphism**: Translucent UI elements with blur effects
- **Minimal Chrome**: Clean interface that puts content first
- **Smooth Animations**: Cubic-bezier(0.4, 0, 0.2, 1) transitions
- **Subtle Borders**: Thin borders (1px) with low opacity
- **Content Focus**: Media cards and artwork are the visual priority

```css
/* Deference Implementation */
background: #000000;
backdrop-filter: blur(40px) saturate(180%);
transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
border: 1px solid rgba(255, 255, 255, 0.1);
```

### 3. Depth

**Apple's Principle**: Distinct visual layers and realistic motion convey hierarchy, impart vitality, and facilitate understanding.

**JellyTV Implementation**:
- **Layering**: Multiple z-index layers (background, content, header, modals)
- **Shadows**: Card shadows that create elevation (0 10px 30px rgba(0, 0, 0, 0.5))
- **Hover Effects**: Cards scale and lift on hover (scale(1.08) translateY(-8px))
- **Focus States**: White glow for keyboard/remote navigation
- **Gradient Overlays**: Linear gradients on backdrops for depth
- **Parallax Motion**: Transform properties for depth perception

```css
/* Depth Implementation */
.card {
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.card:hover {
    transform: scale(1.08) translateY(-8px);
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.7);
    z-index: 10;
}
```

## tvOS-Specific Design Patterns

### The Focus Engine

**Apple's Core Concept**: tvOS uses the Focus Engine to manage user interaction through the Siri Remote.

**Key Principles**:
1. **Focus State**: One element has focus at a time
2. **Visual Feedback**: Focused elements are larger and elevated
3. **Parallax Effect**: Subtle 3D layering on focus (floating appearance)
4. **Directional Navigation**: Up, down, left, right with the remote
5. **Haptic Feedback**: Gentle feedback through the remote

**JellyTV Focus Implementation**:
```css
/* Base State */
.card {
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* Focused State - Key tvOS Pattern */
.card:focus,
.card:hover {
    /* Elevation: Scale up and lift */
    transform: scale(1.08) translateY(-8px);
    
    /* Enhanced shadow for depth */
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.7);
    
    /* White glow (Apple's signature focus indicator) */
    outline: none;
    box-shadow: 0 0 0 6px rgba(255, 255, 255, 0.3),
                0 15px 40px rgba(0, 0, 0, 0.7);
    
    /* Higher z-index to appear above other cards */
    z-index: 10;
}
```

**Focus Behavior**:
- **Scale**: 1.05-1.08x (Apple uses 8% scale typically)
- **Shadow Expansion**: Larger, more diffused shadow
- **White Ring**: 6px white glow with 30% opacity
- **Lift**: Slight upward translation (-8px to -12px)
- **Animation**: 300ms with ease-out timing

### Layering System

**Apple's Pattern**: tvOS uses distinct layers to create visual hierarchy.

**Layer Order (back to front)**:
1. **Background Layer**: Backdrop images, gradients
2. **Content Layer**: Media cards, lists
3. **UI Layer**: Navigation, buttons
4. **Modal Layer**: Dialogs, sheets
5. **Top Bar Layer**: Header with glassmorphism

**JellyTV Layering**:
```css
/* Layer 1: Background */
.backgroundContainer {
    z-index: 0;
    background: linear-gradient(180deg, #000000 0%, #0a0a0a 50%, #000000 100%);
}

/* Layer 2: Content */
.card {
    z-index: 1;
}

/* Layer 3: Focused Content */
.card:focus {
    z-index: 10;
}

/* Layer 4: Navigation */
.skinHeader {
    z-index: 100;
    backdrop-filter: blur(40px) saturate(180%);
}

/* Layer 5: Modals */
.dialog {
    z-index: 1000;
}
```

### Parallax Effect

**Apple's Pattern**: On Apple TV, focused cards show subtle parallax with layered elements.

**Implementation Concept** (requires JavaScript, but CSS provides foundation):
```css
/* Prepare for parallax layers */
.card {
    transform-style: preserve-3d;
    perspective: 1000px;
}

/* Layer separation for parallax */
.cardImage {
    transform: translateZ(20px);
}

.cardText {
    transform: translateZ(40px);
}
```

### Top Shelf

**Apple's Pattern**: The top shelf is a prominent banner at the top of the home screen.

**JellyTV Implementation** (for featured content):
```css
/* Hero/Featured Section */
.heroSection {
    min-height: 60vh;
    background-size: cover;
    background-position: center;
    position: relative;
}

.heroSection::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 50%;
    background: linear-gradient(0deg, #000000 0%, transparent 100%);
}
```

### Buttons and Interactive Elements

**Apple's Guideline**: Buttons should be large, with clear labels and proper spacing for remote navigation.

**JellyTV Implementation**:
- Large touch targets (minimum 44px height)
- Prominent Play button with high contrast (white on black)
- Rounded corners (12-20px border-radius)
- Clear hover states

```css
.btnPlay {
    background: #ffffff;
    color: #000000;
    font-weight: 700;
    padding: 16px 48px;
    border-radius: 20px;
    font-size: 17px;
}
```

### Cards and Content

**Apple's Guideline**: Use cards to group related content with clear visual hierarchy.

**tvOS Card Specifications**:

1. **Lockup Types** (Apple's card terminology):
   - **Poster**: 2:3 aspect ratio (movie/TV show posters)
   - **Landscape**: 16:9 aspect ratio (episode thumbnails)
   - **Square**: 1:1 aspect ratio (albums, apps)
   - **Wide**: Ultra-wide for featured content

2. **Card Anatomy**:
   - **Image**: Primary visual content
   - **Title**: Below image, SF Pro Display, 17-20px
   - **Subtitle**: Below title, SF Pro Text, 15px, 70% opacity
   - **Metadata**: Additional info (year, duration, etc.)
   - **Progress Bar**: 4px height at bottom of image

3. **Spacing Between Cards**:
   - Minimum: 40px horizontal, 60px vertical
   - Standard: 50px horizontal, 80px vertical
   - Generous: 60px+ for premium layouts

**JellyTV Implementation**:
```css
/* Poster Cards (2:3) */
.portraitCard .cardScalable {
    aspect-ratio: 2 / 3;
    border-radius: 16px;
    overflow: hidden;
}

/* Landscape Cards (16:9) */
.backdropCard .cardScalable {
    aspect-ratio: 16 / 9;
    border-radius: 12px;
}

/* Card Grid Spacing */
.itemsContainer.vertical-wrap {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 32px; /* Generous spacing for TV viewing */
}

/* Card Title */
.cardText {
    font-size: 17px;
    font-weight: 600;
    color: #ffffff;
    margin-top: 12px;
}

/* Card Subtitle */
.cardText-secondary {
    font-size: 15px;
    font-weight: 400;
    color: rgba(255, 255, 255, 0.6);
}

/* Progress Bar */
.itemProgressBar {
    height: 4px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 2px;
}

.itemProgressBarForeground {
    background: #0a84ff;
    border-radius: 2px;
}
```

### Content Layout Patterns

**Apple's Common Layouts**:

1. **Shelf Layout**: Horizontal scrolling rows of cards
   ```css
   .scrollSlider {
       display: flex;
       overflow-x: auto;
       scroll-behavior: smooth;
       gap: 20px;
       padding: 20px 0;
   }
   ```

2. **Grid Layout**: Vertical grid for library views
   ```css
   .grid {
       display: grid;
       grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
       gap: 32px;
   }
   ```

3. **Hero Layout**: Large featured content at top
   ```css
   .hero {
       height: 60vh;
       background-size: cover;
       background-position: center top;
   }
   ```

### Color

**Apple's Guideline**: Use color purposefully to communicate meaning and establish hierarchy.

**JellyTV Colors**:
- **Background**: Pure black (#000000) for OLED displays
- **Surface**: Dark gray (#1c1c1e) for cards and panels
- **Accent**: System blue (#0a84ff) for interactive elements
- **Success**: Green for play buttons
- **Text**: White with varying opacity for hierarchy

```css
:root {
    --appletv-black: #000000;
    --appletv-gray: #1c1c1e;
    --appletv-accent: #0a84ff;
    --appletv-white: #ffffff;
}
```

### Typography

**Apple's Guideline**: Use the San Francisco font family with appropriate weights and sizes.

**Official Typography Resources**:
- Download SF Pro fonts from: https://developer.apple.com/design/resources/
- SF Pro Display: For large text (19px and above)
- SF Pro Text: For smaller text (below 19px)
- SF Compact: For watchOS (not used in tvOS)

**San Francisco Font Features**:
1. **Optical Sizing**: Automatically adjusts spacing based on size
2. **Dynamic Tracking**: Letter spacing adjusts with font size
3. **Vertical Metrics**: Optimized line height
4. **OpenType Features**: Ligatures, alternates, number spacing

**San Francisco Font Weights**:
- **100-200**: Ultralight/Thin (rarely used in tvOS)
- **300**: Light (secondary text)
- **400**: Regular (body text)
- **500**: Medium (UI elements, buttons)
- **600**: Semibold (emphasis, card titles)
- **700**: Bold (headings, navigation)
- **800-900**: Heavy/Black (large titles, hero text)

**tvOS Typography Scale** (based on Apple's specifications):
```css
/* Large Title (Hero) */
.itemName {
    font-family: 'SF Pro Display', -apple-system;
    font-size: 76px;        /* 76pt in Apple's spec */
    font-weight: 800;       /* Heavy */
    letter-spacing: -0.04em; /* Tight tracking */
    line-height: 1.1;
}

/* Title 1 */
h1, .pageTitle {
    font-size: 48px;        /* 48pt */
    font-weight: 700;       /* Bold */
    letter-spacing: -0.02em;
    line-height: 1.2;
}

/* Title 2 */
h2, .sectionTitle {
    font-size: 32px;        /* 32pt */
    font-weight: 700;
    letter-spacing: -0.015em;
    line-height: 1.25;
}

/* Title 3 */
h3 {
    font-size: 24px;        /* 24pt */
    font-weight: 600;       /* Semibold */
    letter-spacing: -0.01em;
    line-height: 1.3;
}

/* Body (Standard UI text) */
body, p {
    font-family: 'SF Pro Text', -apple-system;
    font-size: 29px;        /* 29pt - Apple's standard for tvOS */
    font-weight: 400;       /* Regular */
    letter-spacing: -0.005em;
    line-height: 1.4;
}

/* Callout (Card titles) */
.cardText {
    font-size: 25px;        /* 25pt */
    font-weight: 600;
    letter-spacing: -0.005em;
}

/* Caption 1 (Metadata) */
.cardText-secondary {
    font-size: 23px;        /* 23pt */
    font-weight: 400;
    letter-spacing: -0.003em;
    color: rgba(255, 255, 255, 0.6);
}

/* Caption 2 (Small info) */
.itemMiscInfo {
    font-size: 20px;        /* 20pt */
    font-weight: 400;
    letter-spacing: 0;
    color: rgba(255, 255, 255, 0.5);
}
```

**Note on Web Implementation**: 
Since we're using web CSS, we use pixel values instead of points. The actual sizes in JellyTV are optimized for web viewing (17px body instead of 29px) but maintain the same proportional relationships and weights as Apple's tvOS specifications.

### Spacing

**Apple's Guideline**: Use consistent, generous spacing for comfortable viewing distance.

**JellyTV Spacing Scale**:
- **8px** (--spacing-xs): Tight spacing, inline elements
- **12px** (--spacing-sm): Small spacing, compact layouts
- **20px** (--spacing-md): Medium spacing, standard padding
- **32px** (--spacing-lg): Large spacing, section separation
- **48px** (--spacing-xl): Extra large, page margins

### Animation

**Apple's Guideline**: Use animation to provide feedback, show relationships, and guide attention.

**JellyTV Animation Principles**:
- **Duration**: 300-400ms for most transitions
- **Easing**: cubic-bezier(0.4, 0, 0.2, 1) - Apple's standard easing
- **Transform Properties**: Use transform for performance (GPU-accelerated)
- **Purposeful Motion**: Every animation has a purpose

```css
/* Standard Animation */
transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);

/* Hover Animation */
.card:hover {
    transform: scale(1.08) translateY(-8px);
}
```

## Glassmorphism (iOS 13+ / tvOS 13+)

**Apple's Material**: Translucent materials that show content behind UI.

**JellyTV Implementation**:
```css
background: rgba(28, 28, 30, 0.72);
backdrop-filter: blur(40px) saturate(180%);
-webkit-backdrop-filter: blur(40px) saturate(180%);
border: 1px solid rgba(255, 255, 255, 0.1);
```

**Blur Levels**:
- **Light blur**: blur(10px) - Subtle effects
- **Medium blur**: blur(20px) - Overlays
- **Heavy blur**: blur(40px) - Navigation bars, modals

## Accessibility

**Apple's Guideline**: Design for everyone, including users with disabilities.

**JellyTV Accessibility Features**:

1. **Keyboard Navigation**: Full support with focus states
2. **High Contrast**: 7:1 contrast ratio for text
3. **Focus Indicators**: Clear white glow on focused elements
4. **Touch Targets**: Minimum 44x44px for interactive elements
5. **Text Legibility**: San Francisco font, proper sizing and spacing
6. **Reduced Motion**: Respects user preferences (can be added)

```css
/* Focus States for Accessibility */
.focusable:focus,
a:focus,
button:focus {
    outline: none;
    box-shadow: 0 0 0 6px rgba(255, 255, 255, 0.3);
}
```

## Remote Control Support

**Apple's Guideline**: Design for the Siri Remote with directional navigation.

**JellyTV Implementation**:
- Large, easily selectable cards
- Clear focus states with white glow
- Proper tab order
- Hover effects also apply to focus
- Adequate spacing between interactive elements

## Responsive Design

**Apple's Guideline**: Adapt to different screen sizes while maintaining design integrity.

**JellyTV Breakpoints**:
```css
/* Mobile */
@media (max-width: 480px) { }

/* Tablet */
@media (max-width: 768px) { }

/* Desktop */
@media (min-width: 769px) { }
```

## Performance Considerations

**Apple's Guideline**: Ensure smooth 60fps animations.

**JellyTV Optimizations**:
1. Use `transform` and `opacity` for animations (GPU-accelerated)
2. Avoid animating `width`, `height`, `margin`, `padding`
3. Use `will-change` sparingly for critical animations
4. Optimize blur effects for older devices
5. Use `contain` property for layout optimization

```css
/* Optimized Animation */
.card {
    will-change: transform;
    transform: translateZ(0); /* Force GPU acceleration */
}
```

## Design System Comparison

### Apple TV vs JellyTV

| Element | Apple TV | JellyTV Implementation |
|---------|----------|------------------------|
| Background | Pure black | `#000000` |
| Cards | Rounded, elevated | 16px radius, shadows |
| Focus | White glow + scale | `scale(1.08)` + white glow |
| Typography | SF Pro Display/Text | System fallback to SF |
| Blur | 40-60px | 40px backdrop-filter |
| Accent | System blue | `#0a84ff` |
| Animations | 300-400ms | cubic-bezier(0.4, 0, 0.2, 1) |

## Best Practices

### DO ✅

- Use generous spacing (Apple TV is viewed from distance)
- Keep text large and readable (minimum 17px)
- Use consistent border radius (8px, 12px, 16px, 20px)
- Implement clear focus states for remote navigation
- Use dark backgrounds to let content shine
- Apply glassmorphism for modern look
- Keep animations smooth and purposeful
- Support keyboard and remote control navigation

### DON'T ❌

- Don't use small text (under 15px)
- Don't create cluttered interfaces
- Don't skip focus states
- Don't use jarring animations
- Don't compete with content (keep UI subtle)
- Don't ignore accessibility
- Don't forget mobile responsiveness
- Don't use bright backgrounds that strain eyes

## Resources

### Official Apple Resources

**Design Guidelines**:
- **Human Interface Guidelines**: https://developer.apple.com/design/human-interface-guidelines
- **tvOS Guidelines**: https://developer.apple.com/design/human-interface-guidelines/tvos
- **Designing for tvOS**: https://developer.apple.com/design/human-interface-guidelines/designing-for-tvos
- **Platforms Overview**: https://developer.apple.com/design/human-interface-guidelines/platforms

**Design Assets** (from https://developer.apple.com/design/resources/):
- **SF Pro Fonts**: Download San Francisco Pro Display and Text
- **SF Symbols**: 5,000+ configurable symbols
- **tvOS UI Kit**: Sketch, Figma, and Adobe XD templates
- **tvOS App Icon Template**: For creating app icons
- **Color Profiles**: Display P3 and sRGB color profiles
- **Design Templates**: Pre-made layouts and components

**Available Downloads**:
1. **Production Resources**:
   - SF Pro (TrueType and OpenType)
   - SF Compact (for watchOS)
   - SF Mono (for code)
   - SF Arabic, SF Symbols
   
2. **Design Templates**:
   - Sketch Library
   - Figma UI Kit
   - Adobe XD Kit
   - Keynote Templates

3. **tvOS Specific**:
   - Focus Engine Templates
   - Lockup Designs
   - App Icon Templates
   - Top Shelf Templates

**Video Resources**:
- **WWDC Sessions**: Search "Design for tvOS" on Apple Developer
- **Tech Talks**: UI design best practices
- **Sample Code**: UIKit and SwiftUI examples

### Community Resources

**Typography**:
- **System Font Stack**: `-apple-system, BlinkMacSystemFont, "SF Pro Display"`
- **Web Font Alternatives**: Inter, Roboto (close approximations)
- **Google Fonts**: `@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap')`

**Design Tools**:
- **Color Picker**: Apple's Digital Color Meter app
- **SF Symbols App**: Browse all Apple symbols
- **Figma**: Community tvOS UI kits

**Reference Sites**:
- **Apple TV+ Website**: Study their web implementation
- **Apple's Marketing Pages**: Typography and layout examples

## Conclusion

JellyTV implements Apple's Human Interface Guidelines to create an authentic Apple TV experience in Jellyfin. Every design decision—from typography to animations—is based on Apple's principles of Clarity, Deference, and Depth.

By following these guidelines, JellyTV ensures that:
- Content is always the focus
- Navigation is intuitive
- The interface is beautiful and functional
- Users feel at home if they use Apple TV
- Accessibility is built-in from the start

---

**For implementation details, see `jellyfin-appletv.css`**
