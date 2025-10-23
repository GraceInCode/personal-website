# Customization Guide - Making It Uniquely Yours

## What Changed

Your portfolio now has a unique, code-themed identity inspired by "GraceInCode":

### Visual Changes
- **Color Palette**: Emerald green (#10b981) + Blue (#3b82f6) - inspired by code editors
- **Logo**: Wrapped in code brackets `{ GraceInCode }`
- **Curved Sections**: Organic wave dividers between sections
- **Gradient Text**: Headings use multi-color gradients
- **Code Decorations**: Section titles wrapped in `< />` brackets

### Interactive Enhancements
- **Typewriter Effect**: Tagline types out on page load
- **Parallax Hero**: Hero content moves subtly on scroll
- **Staggered Animations**: Cards and skills fade in sequentially
- **Hover Effects**: 
  - Nav links get animated underlines
  - Project cards lift with gradient glow
  - Tech tags transform on hover
  - Buttons have ripple effects
- **Asymmetric Layout**: Even-numbered project cards offset slightly

### Typography
- **Monospace fonts** for tech tags and tagline (code-like)
- **Gradient text** on logo and tagline
- **Code symbols** (>, <, /, {, }) as decorative elements

## Further Customization

### 1. Change Colors

Edit `styles.css` lines 9-19:

```css
:root {
    --primary-color: #10b981;    /* Main green - change to your preference */
    --secondary-color: #3b82f6;  /* Blue accent */
    --accent-color: #8b5cf6;     /* Purple for variety */
}
```

**Suggested Palettes:**
- **Cyberpunk**: `#00ff9f` + `#00b8ff` + `#ff00ff`
- **Sunset**: `#ff6b6b` + `#feca57` + `#ee5a6f`
- **Ocean**: `#0077b6` + `#00b4d8` + `#90e0ef`
- **Forest**: `#2d6a4f` + `#52b788` + `#95d5b2`

### 2. Adjust Animations

**Speed up/slow down typewriter** (`script.js` line 26):
```javascript
setTimeout(typeWriter, 100);  // Change 100 to 50 (faster) or 200 (slower)
```

**Change parallax intensity** (`script.js` line 120):
```javascript
hero.style.transform = `translateY(${scrolled * 0.3}px)`;  // Change 0.3 to 0.5 (more) or 0.1 (less)
```

**Disable animations** (remove from `script.js`):
- Lines 15-32: Typewriter effect
- Lines 118-124: Parallax effect

### 3. Add Custom SVG Icons

Replace placeholder images with custom SVGs. Create at [Figma](https://figma.com) or [Canva](https://canva.com).

**Example: Add a code icon to hero**

In `index.html` after line 29:
```html
<svg width="60" height="60" viewBox="0 0 24 24" fill="none" style="margin-bottom: 1rem;">
    <path d="M8 6L2 12L8 18M16 6L22 12L16 18M13 3L11 21" 
          stroke="url(#gradient)" stroke-width="2" stroke-linecap="round"/>
    <defs>
        <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
            <stop offset="0%" style="stop-color:#10b981"/>
            <stop offset="100%" style="stop-color:#3b82f6"/>
        </linearGradient>
    </defs>
</svg>
```

### 4. Custom Fonts

Add Google Fonts to `index.html` in `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Update `styles.css`:
```css
body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
}

.tagline, .tech-tag {
    font-family: 'JetBrains Mono', 'Courier New', monospace;
}
```

**Recommended Fonts:**
- **Modern**: Inter, Poppins, DM Sans
- **Code**: JetBrains Mono, Fira Code, Source Code Pro
- **Elegant**: Playfair Display, Crimson Pro

### 5. Personalize Content

**Add personality to hero** (`index.html` line 32):
```html
<p class="hero-description">Turning coffee ☕ into code, one function at a time.</p>
```

**Add emoji to skills** (`index.html` lines 48-53):
```html
<li>⚡ JavaScript (ES6+)</li>
<li>🎨 HTML5 & CSS3</li>
<li>📱 Responsive Design</li>
```

**Add project stats**:
```html
<p><strong>Built in:</strong> 2 weeks | <strong>Lines of code:</strong> 2,500+</p>
```

### 6. Background Patterns

Add subtle code-themed background to hero (`styles.css` after line 88):

```css
.hero::after {
    content: '{ } < /> function() const let var';
    position: absolute;
    top: 20%;
    left: 0;
    right: 0;
    font-size: 8rem;
    font-family: monospace;
    color: rgba(16, 185, 129, 0.03);
    text-align: center;
    pointer-events: none;
    white-space: nowrap;
    overflow: hidden;
}
```

### 7. Dark Mode Toggle

Add to `index.html` in nav (line 20):
```html
<button id="theme-toggle" style="background: none; border: none; cursor: pointer; font-size: 1.5rem;">
    🌙
</button>
```

Add to `script.js`:
```javascript
document.getElementById('theme-toggle').addEventListener('click', () => {
    document.body.classList.toggle('dark-mode');
    // Save preference
    localStorage.setItem('theme', document.body.classList.contains('dark-mode') ? 'dark' : 'light');
});
```

## Free Tools for Further Customization

1. **Colors**: [Coolors.co](https://coolors.co) - Generate palettes
2. **Gradients**: [CSSGradient.io](https://cssgradient.io) - Create custom gradients
3. **Icons**: [Heroicons](https://heroicons.com) - Free SVG icons
4. **Animations**: [Animista](https://animista.net) - CSS animation generator
5. **Fonts**: [Google Fonts](https://fonts.google.com) - Free web fonts
6. **Patterns**: [Hero Patterns](https://heropatterns.com) - SVG backgrounds
7. **Shadows**: [SmoothShadow](https://shadows.brumm.af) - Layered shadows
8. **Waves**: [Get Waves](https://getwaves.io) - SVG wave generator

## Quick Wins

**5-minute improvements:**
1. Change color palette (3 variables)
2. Add emoji to skills
3. Update hero description with personality
4. Add your actual project screenshots
5. Customize contact info

**10-minute improvements:**
1. Add Google Fonts
2. Create custom SVG icon
3. Add background pattern
4. Customize animation speeds
5. Add project stats/metrics

**30-minute improvements:**
1. Implement dark mode
2. Add more interactive hover effects
3. Create custom illustrations
4. Add testimonials section
5. Implement loading animation

## What Makes It Unique Now

✅ Code-themed color palette (not generic purple)
✅ Bracket decorations `{ }` and `< />`
✅ Typewriter effect (dynamic, not static)
✅ Asymmetric project layout (not uniform grid)
✅ Monospace fonts for tech elements
✅ Curved section dividers (organic feel)
✅ Gradient text effects
✅ Custom hover interactions
✅ Parallax scrolling
✅ Staggered animations

Your portfolio now stands out while remaining professional and fast-loading!
