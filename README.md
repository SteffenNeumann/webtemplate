# Web Template - Relume Sitemap Integration

A production-ready, responsive HTML/CSS website template designed for rapid deployment of marketing and consulting websites. Optimized for integration with Relume sitemap data.

## 🚀 Quick Start

### For Direct Use
1. Clone this repository
2. Replace all `[PLACEHOLDER]` values in `index.html` with your content
3. Update CSS variables in `styles.css` with your brand colors
4. Add images to `/content/` directory
5. Open `index.html` in a browser to preview

### For AI-Powered Implementation
1. Export your sitemap from Relume app
2. Provide the sitemap and client information to an AI agent
3. Include the `AI-PROMPT.md` file as instructions
4. AI will generate a fully customized website

## 📋 Features

- **Fully Responsive:** Mobile-first design that works on all devices
- **No Build Process:** Pure HTML/CSS/JS - ready to deploy immediately
- **W3.CSS Framework:** Lightweight, modern CSS framework
- **Font Awesome Icons:** 4.7.0 icon library included
- **Contact Form Ready:** Pre-configured with FormSubmit.co integration
- **Smooth Animations:** Scroll-triggered reveal effects
- **Customizable Theme:** CSS variables for easy color customization
- **SEO Friendly:** Semantic HTML with proper meta tags
- **Accessibility Ready:** ARIA labels and alt text structure

## 📁 Project Structure

```
webtemplate/
├── index.html          # Main HTML template with placeholders
├── styles.css          # Custom CSS with variables for theming
├── AI-PROMPT.md        # Comprehensive AI integration instructions
├── README.md           # This file
├── WARP.md            # WARP AI assistant configuration
└── content/           # Directory for images and assets
    └── (add images here)
```

## 🎨 Template Sections

1. **Navigation**
   - Fixed top navigation bar
   - Responsive mobile sidebar menu
   - Smooth anchor scrolling

2. **Hero Section**
   - Full-width gradient background
   - Large headline with CTA button
   - Customizable text content

3. **About Section**
   - Image + text layout
   - Multiple paragraph support
   - Responsive grid

4. **Services Section**
   - 3-column card grid
   - Font Awesome icons
   - Expandable to more services

5. **Portfolio/Features**
   - Alternating left/right layout
   - Image showcase
   - Bullet point support
   - Scroll reveal animations

6. **Contact Section**
   - Functional contact form
   - FormSubmit.co integration
   - Captcha support

7. **Footer**
   - Social media links
   - Copyright information
   - Privacy policy link

8. **Additional Features**
   - Back-to-top button
   - Mobile navigation
   - Smooth scroll behavior

## 🔧 Customization Guide

### Updating Brand Colors

Edit `styles.css` (lines 4-15):
```css
:root {
    --primary-color: #7869E6;      /* Main brand color */
    --secondary-color: #4A90E2;    /* Secondary brand color */
    --accent-color: #FF6B6B;       /* Accent highlights */
    --dark-bg: #2C3E50;            /* Dark backgrounds */
    --light-bg: #F8F9FA;           /* Light backgrounds */
}
```

### Replacing Content Placeholders

Search for and replace these in `index.html`:

**Company Information:**
- `[COMPANY_NAME]`
- `[COMPANY_DESCRIPTION]`
- `[TAGLINE]`
- `[YEAR]`

**Hero Section:**
- `[HERO_TITLE]`
- `[HERO_SUBTITLE]`
- `[HERO_DESCRIPTION]`

**About Section:**
- `[ABOUT_TITLE]`
- `[ABOUT_PARAGRAPH_1/2/3]`

**Services:**
- `[SERVICES_DESCRIPTION]`
- `[SERVICE_1/2/3_TITLE]`
- `[SERVICE_1/2/3_DESCRIPTION]`
- `[ICON_1/2/3]` (Font Awesome icon names)

**Features:**
- `[FEATURE_1/2_TITLE]`
- `[FEATURE_1/2_DESCRIPTION]`
- `[FEATURE_1/2_POINT_1/2/3]`

**Contact:**
- `[CONTACT_DESCRIPTION]`
- `[YOUR_EMAIL]` (FormSubmit email)
- `[YOUR_WEBSITE_URL]`

**Footer:**
- `[SOCIAL_FACEBOOK/INSTAGRAM/TWITTER/LINKEDIN]`
- `[FOOTER_TEXT]`

### Adding Images

1. Place images in `/content/` directory
2. Use descriptive filenames: `team-photo.jpg`, `office-building.jpg`
3. Update image references in HTML:
   ```html
   <img src="content/your-image.jpg" alt="Description">
   ```

### Adding/Removing Sections

To add more service cards:
```html
<div class="w3-col l4 m6 s12 w3-margin-bottom">
    <div class="c-card w3-white w3-card-4" style="padding: 30px; border-radius: 8px; min-height: 350px;">
        <i class="fa fa-icon-name w3-text-metro-light-blue" style="font-size: 48px;"></i>
        <h3>Service Title</h3>
        <p>Service description</p>
    </div>
</div>
```

## 📧 Contact Form Setup

The template uses [FormSubmit.co](https://formsubmit.co/) for form handling:

1. Replace `[YOUR_EMAIL]` with your email address
2. First submission will trigger a verification email from FormSubmit
3. Click the verification link
4. Form will be active and send submissions to your email

**Form Configuration:**
```html
<form action="https://formsubmit.co/your@email.com" method="POST">
    <input type="hidden" name="_captcha" value="true">
    <input type="hidden" name="_next" value="https://yourwebsite.com">
    <!-- form fields -->
</form>
```

## 🤖 AI Integration with Relume

This template is designed to work seamlessly with Relume sitemap exports. See `AI-PROMPT.md` for complete instructions.

**Basic Workflow:**
1. Create sitemap in Relume app
2. Export sitemap data
3. Provide to AI with `AI-PROMPT.md` as instructions
4. AI generates customized website
5. Review and deploy

## 🌐 Deployment Options

### Option 1: W3Schools Spaces
- Upload all files via W3Schools Spaces dashboard
- Built-in hosting and domain support

### Option 2: GitHub Pages
```bash
git add .
git commit -m "Initial website commit"
git push origin main
```
- Enable GitHub Pages in repository settings
- Select `main` branch as source

### Option 3: Netlify/Vercel
- Drag and drop the entire folder
- Automatic deployment on push

### Option 4: Traditional Web Hosting
- Upload files via FTP
- Ensure `index.html` is in root directory

## 🔍 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📱 Responsive Breakpoints

- **Desktop:** > 992px
- **Tablet:** 601px - 992px
- **Mobile:** ≤ 600px

## 🎓 Learning Resources

- **W3.CSS Documentation:** https://www.w3schools.com/w3css/
- **Font Awesome Icons:** https://fontawesome.com/v4.7.0/icons/
- **HTML/CSS Basics:** https://www.w3schools.com/
- **FormSubmit Guide:** https://formsubmit.co/

## 📝 Checklist Before Launch

- [ ] All placeholders replaced
- [ ] Images optimized and added
- [ ] Contact form email configured
- [ ] Brand colors updated in CSS
- [ ] Social media links added
- [ ] Meta descriptions customized
- [ ] Favicon added
- [ ] Privacy policy created (if needed)
- [ ] Test on multiple devices
- [ ] Test in different browsers
- [ ] Verify form submissions work
- [ ] Check all links functional
- [ ] Optimize for page speed
- [ ] Add analytics code (optional)

## 🆘 Common Issues

**Problem:** Images not showing
- **Solution:** Check file path, ensure images are in `/content/` folder

**Problem:** Form not working
- **Solution:** Verify email in FormSubmit URL, check for verification email

**Problem:** Mobile menu not opening
- **Solution:** Ensure JavaScript is enabled, check for console errors

**Problem:** Sections not aligned
- **Solution:** Verify closing tags, check W3.CSS grid classes

## 📄 License

This template is provided as-is for commercial and personal use. No attribution required.

## 🤝 Contributing

This is a simple template. Feel free to fork and customize for your needs.

## 📞 Support

For issues with:
- **Template structure:** Review this README and `AI-PROMPT.md`
- **W3.CSS:** Check [W3.CSS documentation](https://www.w3schools.com/w3css/)
- **FormSubmit:** Visit [formsubmit.co](https://formsubmit.co/)
- **Relume integration:** See `AI-PROMPT.md` for detailed workflow

## 🔄 Version History

- **v1.0** - Initial template release
  - Responsive design
  - W3.CSS integration
  - FormSubmit contact form
  - AI-ready structure
  - Relume sitemap compatibility

---

**Created for rapid web development and AI-powered site generation.**
