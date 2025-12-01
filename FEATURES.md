# Interactive Features Guide

## Card Flip Functionality

### Overview
Service cards now have interactive flip functionality that reveals detailed information on the back side.

### How It Works

**Front Side:**
- Service icon
- Service title
- Brief description
- "Learn More" button

**Back Side:**
- Banner image
- Close button (top-right)
- Service title (H1)
- Detailed description (2-3 paragraphs)
- Benefit list (3 items with checkmarks)

### User Interaction

1. **Flip Card:** Click "Learn More" button
2. **Animation:** Card flips and zooms to fullscreen
3. **Backdrop:** Dark overlay with blur appears
4. **Close:** Click X button, press ESC, or click backdrop

### Customization

#### HTML Structure
```html
<div class="c-card w3-white w3-card-4">
    <div class="card-flip-container">
        <div class="card-front">
            <i class="fa fa-icon"></i>
            <h3>Service Title</h3>
            <p>Brief description</p>
            <button class="btn-mehr-erfahren" onclick="flipCard(this)">Learn More</button>
        </div>
        <div class="card-back">
            <button class="btn-close-card" onclick="closeCard(this)">
                <i class="fa fa-times"></i>
            </button>
            <div class="card-back-banner">
                <img src="content/service-image.jpg" alt="Service">
            </div>
            <div class="card-back-content">
                <h1>Service Title</h1>
                <p>Detailed paragraph 1...</p>
                <p>Detailed paragraph 2...</p>
                <ul class="benefit-list">
                    <li>Benefit 1</li>
                    <li>Benefit 2</li>
                    <li>Benefit 3</li>
                </ul>
            </div>
        </div>
    </div>
</div>
```

#### CSS Variables
Customize appearance in `styles.css`:
```css
:root {
    --accent-color: #FF6B6B;  /* Learn More button color */
    --primary-color: #7869E6;  /* Title colors */
}
```

#### JavaScript Functions
- `flipCard(button)` - Flips and zooms card
- `closeCard(button)` - Closes and unflips card
- `closeAllCards()` - Closes all open cards

### Placeholders for Card Content

**Front Side:**
- `[SERVICE_X_TITLE]` - Service name
- `[SERVICE_X_DESCRIPTION]` - Brief description (1-2 sentences)
- `[ICON_X]` - Font Awesome icon name

**Back Side:**
- `[SERVICE_X_DETAIL_PARAGRAPH_1]` - Detailed explanation (2-3 sentences)
- `[SERVICE_X_DETAIL_PARAGRAPH_2]` - Additional details (2-3 sentences)
- `[SERVICE_X_BENEFIT_1/2/3]` - Three specific benefits
- `content/placeholder-service-X.jpg` - Banner image

### Responsive Behavior

**Desktop (> 768px):**
- Card zooms to 90% width, max 800px
- 150px banner height
- 40px content padding

**Mobile (≤ 768px):**
- Card zooms to 95% width
- 120px banner height
- 20px content padding

---

## Dark/Light Theme Toggle

### Overview
Users can switch between light and dark themes. Preference is saved in browser localStorage.

### Features

- **Toggle Button:** Fixed position (bottom-right, above back-to-top button)
- **Icons:** Moon icon for light mode, sun icon for dark mode
- **Persistence:** Theme choice saved and restored on page reload
- **Smooth Transition:** All colors transition smoothly

### Usage

**For Users:**
1. Click theme toggle button (bottom-right)
2. Page switches to dark/light theme
3. Preference automatically saved

**For Developers:**
Toggle programmatically:
```javascript
toggleTheme(); // Switch theme
```

Check current theme:
```javascript
document.body.classList.contains('dark-theme'); // Returns true/false
```

### Dark Theme Colors

```css
body.dark-theme {
    background-color: #1a1f26;
    color: #e0e0e0;
}

/* Cards */
.dark-theme .w3-white {
    background-color: #2a2f36;
}

/* Accents */
.dark-theme .title-span {
    color: #4dd0e1; /* Cyan */
}

.dark-theme .benefit-list li:before {
    color: #4dd0e1; /* Cyan checkmarks */
}
```

### Customizing Dark Theme

Edit `styles.css` lines 533-614 to adjust dark theme colors:

```css
body.dark-theme {
    background-color: #YOUR_DARK_BG;
    color: #YOUR_TEXT_COLOR;
}

body.dark-theme .title-span {
    color: #YOUR_ACCENT_COLOR;
}
```

### localStorage API

Theme stored as:
```javascript
localStorage.setItem('theme', 'dark');  // or 'light'
localStorage.getItem('theme');          // Retrieve saved theme
```

---

## Keyboard Navigation

### ESC Key
Press `ESC` to close any open card details.

### Implementation
```javascript
document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape') {
        closeAllCards();
    }
});
```

---

## Browser Support

### Card Flip Features
- ✅ Chrome 36+
- ✅ Firefox 16+
- ✅ Safari 9+
- ✅ Edge 12+
- ✅ iOS Safari 9+
- ✅ Chrome Mobile

**CSS Features Used:**
- `transform-style: preserve-3d`
- `backface-visibility`
- `backdrop-filter` (graceful degradation)

### Theme Toggle
- ✅ All modern browsers with localStorage support
- ✅ Fallback: Light theme if localStorage unavailable

---

## Accessibility

### Card Flip
- **Keyboard:** Buttons are focusable and keyboard accessible
- **Screen Readers:** Proper button labels and ARIA structure
- **Focus Management:** Focus trapped when card is open

### Theme Toggle
- **Button Label:** Consider adding aria-label="Toggle dark mode"
- **Icon Change:** Visual indication of current theme
- **No Flashing:** Smooth transition prevents flashing

---

## Performance

### Optimizations
- **CSS Transforms:** Hardware-accelerated animations
- **Transitions:** Smooth 0.6s timing for natural feel
- **Minimal Reflows:** Fixed positioning during animation
- **localStorage:** Fast read/write for theme preference

### Best Practices
1. **Image Optimization:** Compress banner images to < 500KB
2. **Lazy Loading:** Consider lazy loading card back content
3. **Debounce:** Window resize events are not used (good!)

---

## Testing Checklist

### Card Flip
- [ ] Click "Learn More" button flips card
- [ ] Card zooms to fullscreen
- [ ] Backdrop appears with blur
- [ ] Close button works
- [ ] ESC key closes card
- [ ] Click backdrop closes card
- [ ] Multiple cards can't be open simultaneously
- [ ] Scrolling disabled when card open
- [ ] Mobile responsive sizing works
- [ ] Content readable on small screens

### Theme Toggle
- [ ] Toggle button visible
- [ ] Icon changes (moon ↔ sun)
- [ ] Colors switch correctly
- [ ] Theme persists on page reload
- [ ] Works in private/incognito mode (if localStorage available)
- [ ] All sections adapt to theme
- [ ] Text remains readable in both themes
- [ ] Forms styled in both themes
- [ ] Navigation styled in both themes

### Cross-Browser
- [ ] Chrome (desktop & mobile)
- [ ] Firefox
- [ ] Safari (desktop & iOS)
- [ ] Edge

---

## Troubleshooting

**Card won't flip:**
- Check JavaScript is enabled
- Verify button has `onclick="flipCard(this)"`
- Check browser console for errors

**Card stuck open:**
- Press ESC key
- Refresh page
- Check for JavaScript errors

**Theme not persisting:**
- Check localStorage is enabled
- Try non-private browsing mode
- Clear browser cache

**Backdrop not showing:**
- Verify `#cardBackdrop` element exists
- Check z-index conflicts
- Ensure CSS loaded correctly

**Mobile card too large:**
- Check viewport meta tag present
- Verify responsive CSS loaded
- Test in device mode, not just resize

---

## Future Enhancements

Potential additions:
- Swipe gesture to close on mobile
- Card history navigation (back button)
- Multiple card views side-by-side (desktop)
- Animated transitions between cards
- Auto-close after timeout
- Share button on card back
- Print card details
- More theme options (blue, purple, etc.)

---

## Credits

- **Card Flip:** CSS 3D transforms
- **Theme Toggle:** localStorage API
- **Icons:** Font Awesome 4.7.0
- **Animations:** CSS transitions and transforms
