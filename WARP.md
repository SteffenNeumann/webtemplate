# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

**webtemplate** is a production-ready HTML/CSS website template designed for rapid deployment and AI-powered implementation. It serves as a base for creating marketing and consulting websites, with specific optimization for Relume sitemap integration.

## Core Architecture

### Technology Stack
- **Frontend:** Pure HTML5, CSS3, vanilla JavaScript
- **CSS Framework:** W3.CSS from W3Schools CDN
- **Icons:** Font Awesome 4.7.0
- **Forms:** FormSubmit.co for contact form handling
- **Hosting:** Flexible (W3Schools Spaces, GitHub Pages, Netlify, traditional hosting)
- **No build process:** Direct HTML/CSS/JS files

### File Structure
```
webtemplate/
├── index.html          # Main HTML template with [PLACEHOLDER] markers
├── styles.css          # Custom CSS with CSS variables for theming
├── AI-PROMPT.md        # Comprehensive instructions for AI implementation
├── README.md           # User documentation
├── WARP.md            # This file
└── content/           # Directory for images and assets
```

### Key Design Patterns

**Placeholder System:** The template uses a `[PLACEHOLDER]` convention for easy find-and-replace:
- Format: `[DESCRIPTIVE_NAME]` in ALL CAPS with underscores
- Examples: `[COMPANY_NAME]`, `[HERO_TITLE]`, `[SERVICE_1_DESCRIPTION]`
- All placeholders must be replaced before deployment

**CSS Variables:** Centralized theming via CSS custom properties in `styles.css`:
```css
:root {
    --primary-color: #7869E6;
    --secondary-color: #4A90E2;
    --accent-color: #FF6B6B;
    /* Additional variables for spacing, typography, shadows */
}
```

**Layout Architecture:**
- Single-page sections with anchor navigation (#home, #about, #services, #portfolio, #contact)
- W3.CSS grid system for responsive layouts
- Mobile-first responsive design
- Fixed navigation with mobile hamburger menu
- CSS classes: `.container`, `.hero`, `.c-card`, `.c-card-right`, `.reveal`

**Component Structure:**
- **Hero:** Gradient background, centered content
- **About:** 2-column image + text layout
- **Services:** 3-column card grid (expandable)
- **Portfolio/Features:** Alternating left/right content blocks
- **Contact:** Functional form with FormSubmit.co
- **Footer:** Social links, copyright, privacy policy link

## Common Development Tasks

### Local Development
```bash
# No build process needed - open directly in browser
open index.html

# OR use local server for accurate testing
python3 -m http.server 8000
# Navigate to http://localhost:8000
```

### Creating a New Site from Template

**Manual Process:**
1. Replace all placeholders in `index.html`
2. Update CSS variables in `styles.css` with brand colors
3. Add images to `/content/` directory
4. Update image references in HTML
5. Configure FormSubmit email in contact form

**AI-Assisted Process:**
1. Gather Relume sitemap data
2. Collect client information (company name, colors, content, etc.)
3. Provide `AI-PROMPT.md` to AI agent with client data
4. Review generated output
5. Deploy

### Adding New Sections

**Service Card:**
```html
<div class="w3-col l4 m6 s12 w3-margin-bottom">
    <div class="c-card w3-white w3-card-4" style="padding: 30px; border-radius: 8px; min-height: 350px;">
        <i class="fa fa-icon-name w3-text-metro-light-blue" style="font-size: 48px;"></i>
        <h3>Service Title</h3>
        <p>Service description</p>
    </div>
</div>
```

**Feature Block (Left Image):**
```html
<div class="c-card reveal" style="margin: 60px 0;">
    <div class="w3-row-padding">
        <div class="w3-col l6 m12">
            <img src="content/image.jpg" alt="Description" style="width:100%; border-radius: 8px;" class="w3-card-4">
        </div>
        <div class="w3-col l6 m12" style="padding: 40px 20px;">
            <h3>Feature Title</h3>
            <p>Feature description</p>
        </div>
    </div>
</div>
```

**Feature Block (Right Image):**
```html
<div class="c-card-right reveal" style="margin: 60px 0;">
    <div class="w3-row-padding">
        <div class="w3-col l6 m12" style="padding: 40px 20px;">
            <h3>Feature Title</h3>
            <p>Feature description</p>
        </div>
        <div class="w3-col l6 m12">
            <img src="content/image.jpg" alt="Description" style="width:100%; border-radius: 8px;" class="w3-card-4">
        </div>
    </div>
</div>
```

### Version Control Workflow
**Branch:** `main` (primary branch)

Before starting work:
```bash
git pull
```

After finishing work:
```bash
git add .
git commit -m "Description of changes"
git push
```

## Important Notes

### Placeholder Convention
- **Always use** the `[PLACEHOLDER]` format for variables
- **Never** leave placeholders in production code
- Search for `[` in files to find remaining placeholders before deployment

### Image Path Handling
- Use forward slashes: `content/image-name.jpg`
- Keep naming lowercase with hyphens: `team-meeting.jpg`, not `Team Meeting.JPG`
- Optimize images before adding (< 1MB recommended)
- Always include descriptive alt text

### Contact Form Configuration
- Uses FormSubmit.co service
- Endpoint format: `https://formsubmit.co/email@example.com`
- First submission requires email verification
- Hidden fields available: `_captcha`, `_next`, `_subject`, etc.

### CSS Customization
- **Always modify CSS variables** rather than hardcoding colors
- Variables are defined in `:root` selector (lines 4-45 of `styles.css`)
- Use `!important` flags only where W3.CSS conflicts occur

### External Dependencies (CDN)
- W3.CSS: `https://www.w3schools.com/w3css/4/w3.css`
- W3 Color Library: `https://www.w3schools.com/lib/w3-colors-highway.css`
- Font Awesome: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css`

### Responsive Design
- Mobile breakpoint: ≤ 600px
- Tablet breakpoint: 601px - 992px
- Desktop breakpoint: > 992px
- Always test changes on all three breakpoints

## Code Style Guidelines

### HTML
- Use semantic HTML5 elements (`<main>`, `<section>`, `<nav>`, `<footer>`)
- Maintain W3.CSS utility classes: `w3-container`, `w3-col`, `w3-card-4`, etc.
- Keep inline JavaScript event handlers: `onclick="functionName()"`
- Always include async on script tags
- Provide meaningful alt text for all images

### CSS
- Use CSS variables for all themeable properties
- Keep `.container` at 60% width (80% tablet, 90% mobile)
- Maintain consistent spacing with CSS variable system
- Use W3.CSS color classes where possible: `w3-metro-light-blue`, etc.
- Box shadows defined as variables: `--shadow-small/medium/large`

### JavaScript
- Vanilla JS only, no frameworks
- Define functions globally for inline event handlers
- Keep code simple and readable
- Functions: `toggleMobileNavigation()`, `goToTop()`, `scroll()`, `reveal()`
- Scroll-based animations use `.reveal` class with `.active` state

## AI Integration System

### Relume Sitemap Workflow
This template is designed to work with Relume sitemap exports:

1. **Input:** Relume sitemap JSON/data + client information
2. **Process:** AI reads `AI-PROMPT.md` and populates template
3. **Output:** Customized HTML/CSS website ready for deployment

### AI Prompt Structure
The `AI-PROMPT.md` file contains:
- **Phase 1:** Analysis & Mapping (parse sitemap, map components)
- **Phase 2:** Template Customization (update colors, replace placeholders)
- **Phase 3:** Content Population (fill sections with real content)
- **Phase 4:** Multi-Page Implementation (create additional pages if needed)
- **Phase 5:** Quality Assurance (verify all placeholders replaced)

### Component Mapping
| Relume Component | Template Implementation |
|-----------------|------------------------|
| Hero | `#home` hero section |
| Features Grid | `#services` card grid |
| Content Left/Right | `#portfolio` alternating blocks |
| Contact Form | `#contact` FormSubmit form |
| Call to Action | Can be added anywhere |
| Team/Testimonials | Custom sections (examples in AI-PROMPT.md) |

## Deployment Options

### W3Schools Spaces
- Upload all files via dashboard
- Automatic HTTPS
- Custom domain support

### GitHub Pages
```bash
# Enable in repository settings
# Set source to 'main' branch
git push origin main
```

### Netlify/Vercel
- Drag and drop deployment
- Automatic SSL
- Continuous deployment from Git

### Traditional Hosting
- FTP upload to web root
- Ensure `index.html` is in root directory

## Quality Assurance Checklist

Before considering a site complete:
- [ ] All `[PLACEHOLDER]` values replaced (search for `[` in files)
- [ ] CSS variables updated with brand colors
- [ ] All images added to `/content/` directory
- [ ] Image paths correct and images display
- [ ] Contact form email configured
- [ ] Social media links added or removed
- [ ] Navigation links functional
- [ ] Mobile navigation tested
- [ ] Responsive design verified (mobile, tablet, desktop)
- [ ] All sections from requirements implemented
- [ ] Footer year current
- [ ] Meta descriptions unique and descriptive
- [ ] Alt text provided for all images
- [ ] Forms tested and submitting correctly
- [ ] Cross-browser testing completed

## Troubleshooting

**Issue:** Placeholders still visible in production
- **Solution:** Search for `[` in HTML files, replace all instances

**Issue:** Colors not applying correctly
- **Solution:** Check CSS variable syntax, verify `!important` flags on W3.CSS overrides

**Issue:** Images not displaying
- **Solution:** Verify path format (`content/image.jpg`), check file exists

**Issue:** Mobile menu not working
- **Solution:** Verify JavaScript present, check element ID matches (`#mobile-sidenav`)

**Issue:** Form not submitting
- **Solution:** Check FormSubmit URL format, verify email verification completed

**Issue:** Sections misaligned
- **Solution:** Validate HTML, check W3.CSS grid class usage, verify closing tags

## Best Practices

1. **Never hardcode colors** - Always use CSS variables
2. **Always test responsively** - Check mobile, tablet, desktop
3. **Optimize images** - Compress before adding to reduce page load
4. **Keep it simple** - This is a lightweight template, don't over-engineer
5. **Validate HTML** - Use W3C validator before deployment
6. **Semantic naming** - Use descriptive file and variable names
7. **Comment custom code** - Help future developers understand modifications
8. **GDPR compliance** - Add privacy policy if collecting user data
9. **Accessibility** - Maintain ARIA labels and semantic HTML
10. **Performance** - Minimize custom CSS/JS, leverage CDN caching

## Template Modification Guidelines

### When Making Changes
- **Document why** - Add comments explaining non-obvious decisions
- **Test thoroughly** - Verify changes don't break responsive design
- **Maintain placeholder system** - Keep `[PLACEHOLDER]` convention
- **Update documentation** - Modify README.md and AI-PROMPT.md if needed
- **Version control** - Commit with descriptive messages

### What NOT to Change
- W3.CSS CDN links (unless upgrading versions intentionally)
- Core W3.CSS class names
- JavaScript function names (used by inline event handlers)
- HTML structure for responsive grid (breaks mobile layout)
- CSS variable naming scheme

### Safe to Customize
- CSS variable values (colors, spacing, fonts)
- Section content and order
- Number of service cards or feature blocks
- Hero background (gradient can be replaced with image)
- Footer content and social links
- Font families (update in CSS)

## Support Resources

- **W3.CSS Docs:** https://www.w3schools.com/w3css/
- **Font Awesome 4.7.0:** https://fontawesome.com/v4.7.0/icons/
- **FormSubmit.co:** https://formsubmit.co/
- **Relume Library:** https://library.relume.io/
- **HTML Validator:** https://validator.w3.org/

---

**Note:** This template is intentionally simple and dependency-free to maximize compatibility and ease of use for both manual and AI-driven implementation workflows.
