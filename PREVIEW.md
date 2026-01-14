# JellyTV Preview & Examples

This document shows what to expect when using JellyTV - the Apple TV-style theme for Jellyfin.

## 📸 What You'll See

### Before and After Comparison

**Before (Default Jellyfin)**:
- Standard blue accent colors
- Basic card layouts
- Minimal hover effects
- Default system fonts
- Standard shadows

**After (JellyTV Applied)**:
- Apple TV-style dark interface with true black backgrounds
- Glassmorphism effects on headers and navigation
- San Francisco font family (or system equivalents)
- Smooth scale and lift animations on hover
- White focus glow for remote/keyboard navigation
- Generous spacing optimized for viewing distance
- Refined shadows and elevation
- Apple TV blue accent color (#0a84ff)

## 🎨 Key Visual Changes

### 1. Homepage

**Elements Styled**:
```
┌─────────────────────────────────────────────────┐
│  [☰] Jellyfin     🔍 Search      👤 User       │ ← Glassmorphic header
├─────────────────────────────────────────────────┤
│                                                 │
│  Continue Watching                              │ ← SF Pro Display Bold
│  ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐          │
│  │    │ │    │ │    │ │    │ │    │          │ ← Horizontal scroll
│  │ 📺 │ │ 📺 │ │ 📺 │ │ 📺 │ │ 📺 │          │   Cards with hover
│  └────┘ └────┘ └────┘ └────┘ └────┘          │   scale effect
│                                                 │
│  Recently Added Movies                          │
│  ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐          │
│  │🎬  │ │🎬  │ │🎬  │ │🎬  │ │🎬  │          │ ← 2:3 aspect ratio
│  └────┘ └────┘ └────┘ └────┘ └────┘          │   Rounded corners
│                                                 │
└─────────────────────────────────────────────────┘
```

**Visual Features**:
- True black background (#000000)
- Section titles: 32px, SF Pro Display Bold
- Cards with 16px border radius
- 32px gap between cards
- Progress bars at bottom of cards
- Smooth horizontal scrolling

### 2. Movie/Show Detail Page

**Layout**:
```
┌─────────────────────────────────────────────────┐
│                                                 │
│            [Backdrop Image]                     │ ← Gradient overlay
│            50% opacity                          │   from black
│                                                 │
│  ┌────┐                                         │
│  │    │  Movie Title (56px, Heavy)             │ ← Poster (left)
│  │    │  ★★★★☆ 2023 • 2h 15m • PG-13          │   Info (right)
│  │🎬  │                                         │
│  │    │  [▶ Play]  [+ My List]  [Info]        │ ← Action buttons
│  └────┘                                         │
│                                                 │
│  Overview text with 19px SF Pro Text...        │ ← Body text
│                                                 │
│  Cast & Crew                                    │
│  ┌────┐ ┌────┐ ┌────┐                          │ ← Circle avatars
│  │ 👤 │ │ 👤 │ │ 👤 │                          │
│  └────┘ └────┘ └────┘                          │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Visual Features**:
- Backdrop with gradient from 100% black to transparent
- Large title: 56px, SF Pro Display Heavy
- White Play button (stands out like Apple TV)
- Glassmorphic metadata badges
- Circular cast member cards
- Smooth transitions on all interactive elements

### 3. Library Grid View

**Layout**:
```
┌─────────────────────────────────────────────────┐
│  Movies                    [🔲 Grid] [☰ List]  │ ← Tab navigation
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌────┐  ┌────┐  ┌────┐  ┌────┐  ┌────┐      │
│  │🎬  │  │🎬  │  │🎬  │  │🎬  │  │🎬  │      │
│  │    │  │    │  │    │  │    │  │    │      │ ← Responsive grid
│  └────┘  └────┘  └────┘  └────┘  └────┘      │   Auto-fit columns
│  Title   Title   Title   Title   Title        │
│                                                 │
│  ┌────┐  ┌────┐  ┌────┐  ┌────┐  ┌────┐      │
│  │🎬  │  │🎬  │  │🎬  │  │🎬  │  │🎬  │      │
│  └────┘  └────┘  └────┘  └────┘  └────┘      │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Visual Features**:
- Grid: `repeat(auto-fill, minmax(180px, 1fr))`
- 32px gap between cards
- Titles below cards: 17px, SF Pro Display Semibold
- Secondary info: 15px, 60% opacity
- Hover: Scale 1.08 + lift -8px + shadow

### 4. Video Player OSD

**Layout**:
```
┌─────────────────────────────────────────────────┐
│  ← Back to Browse          Episode Title     ⚙ │ ← Top gradient
│                                                 │
│                                                 │
│             [▶ Play/Pause]                      │ ← Center (optional)
│                                                 │
│                                                 │
│  ━━━━━━●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━    │ ← Bottom gradient
│  1:23:45 / 2:15:00                              │   Seek bar
│  [⏮] [⏪] [▶] [⏩] [⏭] [CC] [🔊] [⚙]         │ ← Controls
└─────────────────────────────────────────────────┘
```

**Visual Features**:
- Top gradient: rgba(0,0,0,0.9) to transparent
- Bottom gradient: transparent to rgba(0,0,0,0.9)
- Glassmorphic control bar
- Blue seek bar (#0a84ff)
- Large, touchable controls
- Smooth fade in/out

### 5. Settings & Dialogs

**Modal Example**:
```
        ┌─────────────────────────────┐
        │ Dialog Title            ✕   │ ← Glassmorphic
        ├─────────────────────────────┤   background
        │                             │
        │  Dialog content here with   │ ← 17px body text
        │  proper spacing and clean   │
        │  typography.                │
        │                             │
        │  [Cancel]        [Confirm]  │ ← Action buttons
        └─────────────────────────────┘
```

**Visual Features**:
- Background: rgba(28, 28, 30, 0.72)
- Backdrop blur: 60px
- Border: 1px white at 10% opacity
- 20px border radius
- Drop shadow: 0 20px 60px rgba(0,0,0,0.8)
- Backdrop dimming: rgba(0,0,0,0.7)

## 🎬 Interaction Examples

### Card Hover Animation

```
Normal State:
┌────────────┐
│            │  Scale: 1.0
│   🎬       │  Shadow: 0 10px 30px
│            │  Z-index: 1
└────────────┘

Hover/Focus State:
  ┌──────────────┐
  │              │  Scale: 1.08
  │    🎬        │  Shadow: 0 15px 40px + white glow
  │              │  Z-index: 10
  └──────────────┘  Transform: translateY(-8px)
```

**Animation**: 300ms cubic-bezier(0.4, 0, 0.2, 1)

### Button States

```css
/* Normal */
[▶ Play]
- Background: #0a84ff
- Color: white
- Padding: 12px 32px
- Border-radius: 16px

/* Hover */
[▶ Play]  ← Slightly larger, brighter
- Background: #409cff
- Transform: scale(1.02)

/* Focus (keyboard/remote) */
[▶ Play]  ← White glow outline
- Box-shadow: 0 0 0 6px rgba(255, 255, 255, 0.3)
```

### Sidebar Navigation

```
Normal:
☰ Home
☰ Movies         ← 17px, 500 weight
☰ TV Shows

Hover:
☰ Home
▶ Movies         ← Translate right 4px
☰ TV Shows          Light background

Selected:
☰ Home
▶ Movies         ← 600 weight
☰ TV Shows          Darker background
```

## 🎯 Typography Examples

### Heading Hierarchy

```
LARGE TITLE (56px, Heavy, -0.03em tracking)
Used for: Main item titles on detail pages

Title 1 (48px, Bold, -0.02em tracking)  
Used for: Page titles, major sections

Title 2 (32px, Bold, -0.015em tracking)
Used for: Section titles, shelf headers

Title 3 (24px, Semibold, -0.01em tracking)
Used for: Subsection titles

Body (17px, Regular, -0.01em tracking)
Used for: Standard text, descriptions

Caption (15px, Regular, -0.005em tracking)
Used for: Metadata, secondary information
```

### Font Weight Usage

```
300 Light:     Secondary descriptive text
400 Regular:   Body text, descriptions
500 Medium:    UI elements, labels
600 Semibold:  Card titles, emphasis
700 Bold:      Section headers
800 Heavy:     Large titles, hero text
```

## 🌈 Color Palette

### Primary Colors

```css
Background:    #000000  ████  True black
Surface:       #1c1c1e  ████  Dark gray
Light Surface: #2c2c2e  ████  Light gray
Lighter:       #3a3a3c  ████  Lighter gray
Accent:        #0a84ff  ████  System blue
Accent Hover:  #409cff  ████  Light blue
Text:          #ffffff  ████  White
```

### Opacity Levels

```
100%: Primary text, titles
85%:  Body text
70%:  Secondary text
60%:  Tertiary text, metadata
30%:  Disabled states, borders
15%:  Subtle backgrounds, hover states
10%:  Very subtle borders
```

### Usage Examples

```css
Card Title:        #ffffff (100%)
Card Description:  rgba(255,255,255,0.7) (70%)
Metadata:          rgba(255,255,255,0.6) (60%)
Card Border:       rgba(255,255,255,0.1) (10%)
Hover Background:  rgba(255,255,255,0.15) (15%)
```

## 📐 Spacing System

### Scale

```
8px  (--spacing-xs):  ▌    Tight, inline elements
12px (--spacing-sm):  ▌▌   Small gaps, compact lists
20px (--spacing-md):  ▌▌▌  Standard padding
32px (--spacing-lg):  ▌▌▌▌▌  Section spacing
48px (--spacing-xl):  ▌▌▌▌▌▌▌  Page margins
```

### Application

```
Card Gap:              32px (lg)
Section Margin:        48px (xl)
Button Padding:        12px 32px (sm, lg)
Input Padding:         12px 20px (sm, md)
Modal Padding:         32px (lg)
List Item Padding:     20px (md)
```

## 🎭 Special Effects

### Glassmorphism

```css
/* Header Bar */
background: rgba(28, 28, 30, 0.72);
backdrop-filter: blur(40px) saturate(180%);
border-bottom: 1px solid rgba(255, 255, 255, 0.1);

/* Result: Frosted glass effect with content visible behind */
```

### Gradient Overlays

```css
/* Backdrop Fade */
linear-gradient(180deg, 
    rgba(0,0,0,0.8) 0%, 
    rgba(0,0,0,0.6) 50%, 
    rgba(0,0,0,1) 100%)

/* OSD Top */
linear-gradient(180deg,
    rgba(0,0,0,0.9) 0%,
    rgba(0,0,0,0) 45%)

/* OSD Bottom */
linear-gradient(0deg,
    rgba(0,0,0,0.9) 0%,
    rgba(0,0,0,0) 45%)
```

### Shadows

```css
/* Card Normal */
box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);

/* Card Hover */
box-shadow: 0 15px 40px rgba(0, 0, 0, 0.7);

/* Focus Glow */
box-shadow: 0 0 0 6px rgba(255, 255, 255, 0.3);

/* Combined (focus + elevation) */
box-shadow: 
    0 0 0 6px rgba(255, 255, 255, 0.3),
    0 15px 40px rgba(0, 0, 0, 0.7);
```

## 📱 Responsive Behavior

### Breakpoints

```css
/* Desktop (default) */
Font size: 17px
Card gap: 32px
Padding: 48px

/* Tablet (< 768px) */
Font size: 17px
Card gap: 20px
Padding: 32px

/* Mobile (< 480px) */
Font size: 16px
Card gap: 12px
Padding: 20px
```

### Grid Adaptation

```
Desktop (> 1400px):  7-8 cards per row
Large (1000-1400px): 6-7 cards per row
Medium (768-1000px): 4-5 cards per row
Tablet (480-768px):  3-4 cards per row
Mobile (< 480px):    2-3 cards per row
```

## 🎮 Accessibility Features

### Keyboard Navigation

- **Tab**: Move between interactive elements
- **Enter/Space**: Activate buttons and links
- **Arrow Keys**: Navigate card grids
- **Escape**: Close modals and menus
- **Focus Indicators**: White glow on focused elements

### Visual Accessibility

- **Contrast Ratio**: Minimum 7:1 for text
- **Focus States**: Prominent white glow (6px)
- **Touch Targets**: Minimum 44x44px
- **Text Sizing**: Large, readable fonts
- **Clear Hierarchy**: Distinct heading levels

### Screen Reader Support

- Semantic HTML maintained
- Alt text for images (Jellyfin default)
- ARIA labels preserved
- Proper heading structure

## 💡 Pro Tips

### Best Viewing Experience

1. **Display**: Use on a large screen (32"+ recommended)
2. **Distance**: Optimized for 3-10 feet viewing
3. **Lighting**: Works best in dim/dark rooms
4. **Browser**: Chrome/Edge for best blur effects
5. **Hardware**: GPU acceleration for smooth animations

### Optimization

1. **Disable Blur on Older Devices**: Remove backdrop-filter if laggy
2. **Reduce Animations**: Can disable transforms if needed
3. **Adjust Spacing**: Customize variables for your screen size
4. **Change Accent Color**: Match your preference

### Customization Ideas

```css
/* Gaming Theme - Green Accent */
:root {
    --appletv-accent: #30d158;
}

/* Netflix-style - Red Accent */
:root {
    --appletv-accent: #e50914;
}

/* Compact Mode - Less Spacing */
:root {
    --spacing-lg: 24px;
    --spacing-xl: 36px;
}

/* Larger Text - Better Readability */
body {
    font-size: 19px !important;
}
```

---

## 🎉 Result

With JellyTV applied, your Jellyfin installation will look and feel like a native Apple TV interface with:

✅ Beautiful glassmorphism effects  
✅ Smooth, Apple-quality animations  
✅ Proper typography with SF-style fonts  
✅ Focus states for remote control  
✅ Generous spacing for comfortable viewing  
✅ Dark theme that's easy on the eyes  
✅ Professional, polished appearance  

**Enjoy your Apple TV experience in Jellyfin! 🍎✨**
