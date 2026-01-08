# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a static personal portfolio website built using the **iPortfolio template (v3.7.0)** from BootstrapMade. The site showcases professional experience, skills, projects, certifications, and contact information for Aman Sharma (Analytics Enthusiast / Full Stack Developer).

The website is hosted on **GitHub Pages** and deployed directly from the `master` branch.

## Technology Stack

- **Frontend Framework**: Bootstrap 5.1.3
- **JavaScript**: Vanilla JavaScript (no jQuery - removed in v3.0.0)
- **Template**: iPortfolio by BootstrapMade
- **Hosting**: GitHub Pages (https://amanramanandsharma.github.io/)
- **Backend**: PHP Email Form (for contact form, requires pro version)

### Key Vendor Libraries

Located in `assets/vendor/`:
- **Bootstrap 5.1.3**: CSS framework
- **AOS (Animate On Scroll)**: Scroll animations
- **GLightbox**: Lightbox for portfolio items
- **Isotope Layout**: Portfolio filtering and layout
- **Swiper**: Testimonials/certifications slider
- **Typed.js**: Typing animation effect in hero section
- **Bootstrap Icons & Boxicons**: Icon libraries
- **Waypoints**: Scroll-triggered events
- **PureCounter**: Number counting animations

## Project Structure

```
.
├── index.html              # Main portfolio page
├── inner-page.html         # Generic inner page template
├── portfolio-details.html  # Portfolio item detail template
├── assets/
│   ├── css/
│   │   └── style.css       # Main custom styles
│   ├── js/
│   │   └── main.js         # Main JavaScript (vanilla JS)
│   ├── img/                # Images, profile photos, project screenshots
│   └── vendor/             # Third-party libraries
├── forms/
│   └── contact.php         # Contact form handler (requires PHP Email Form library)
├── changelog.txt           # Template version history
└── Readme.txt             # Template attribution
```

## Development Workflow

### Making Content Updates

All content is directly in `index.html`. Key sections to edit:

1. **Profile Information**: Lines 64-72 (header profile section)
2. **Hero Section**: Lines 87-93 (typing animation text at `data-typed-items`)
3. **Skills**: Lines 98-169
4. **Experience**: Lines 172-242
5. **Projects**: Lines 244-333
6. **Certifications**: Lines 337-388
7. **Contact**: Lines 390-460

### Testing Changes Locally

This is a static HTML site that can be opened directly in a browser:

```bash
open index.html
```

For testing the PHP contact form, you'll need a local PHP server:

```bash
php -S localhost:8000
```

Then visit: http://localhost:8000

### Deploying to GitHub Pages

Changes pushed to the `master` branch are automatically deployed to GitHub Pages:

```bash
git add .
git commit -m "Description of changes

Co-Authored-By: Warp <agent@warp.dev>"
git push origin master
```

The site will be live at: https://amanramanandsharma.github.io/

## Important Customization Notes

### Meta Tags and SEO

Meta tags are defined in the `<head>` section (lines 8-25):
- Update Open Graph tags for social media sharing
- Update Twitter Card metadata
- Ensure `assets/img/metatags.png` exists for social previews

### Contact Form

The contact form (`forms/contact.php`) requires the **PHP Email Form library** (pro version of template). The form sends to: `armslive1904@gmail.com`

To modify:
- Update `$receiving_email_address` in `forms/contact.php`
- Ensure `assets/vendor/php-email-form/php-email-form.php` exists

For SMTP configuration, uncomment and configure lines 27-33 in `forms/contact.php`.

### Adding New Projects

Projects are in the portfolio section (lines 260-330). Each project follows this structure:

```html
<div class="col-lg-4 col-md-6 portfolio-item filter-app">
  <div class="portfolio-wrap">
    <div class="card card-portfolio">
      <div class="card-body">
        <h4 class="card-title"><strong>Project Title</strong></h4>
        <p class="card-text">Description...</p>
        <p class="card-text"><strong>Tools:</strong> Tech stack</p>
      </div>
    </div>
    <div class="portfolio-links">
      <a href="presentation-link" target="_blank" title="presentation"><i class="bx bx-link"></i></a>
      <a href="github-link" target="_blank" title="github"><i class="bx bxl-github"></i></a>
    </div>
  </div>
</div>
```

### Adding Certifications

Certifications use Swiper slider (lines 344-385). Add new slides within `<div class="swiper-wrapper">`:

```html
<div class="swiper-slide">
  <div class="card m-2 border-dark" data-aos="fade-up">
    <img class="card-img-top img-fluid max-height-350" src="assets/img/testimonials/cert-name.png" alt="Certificate">
    <div class="card-body">
      <h5 class="card-title"><strong>Certification Name</strong></h5>
    </div>
  </div>
</div>
```

## JavaScript Architecture

The main JavaScript file (`assets/js/main.js`) is written in **vanilla JavaScript** (no jQuery since v3.0.0). Key functionality:

- **Navigation**: Active state on scroll, smooth scrolling, mobile nav toggle
- **Hero Section**: Typed.js animation for rotating job titles
- **Portfolio**: Isotope layout and filtering
- **Animations**: AOS (Animate On Scroll) integration
- **Lightbox**: GLightbox for portfolio items
- **Skills Progress**: Waypoints-triggered progress bar animations

## CSS Customization

Main styles are in `assets/css/style.css`:

- **Theme Colors**: Primary color is `#149ddd` (blue)
- **Layout**: Fixed sidebar (300px width) on desktop, mobile-responsive
- **Typography**: Open Sans (body), Raleway & Poppins (headings)
- **Responsive Breakpoint**: 1199px (sidebar collapses to mobile menu)

## Common Tasks

### Update Resume Link

Line 165 in `index.html`:
```html
<a class="btn btn-primary" href="GOOGLE_DRIVE_LINK" target="_blank">View Resume</a>
```

### Change Profile Photo

Replace `assets/img/profile_aman_github.jpeg` and update line 65:
```html
<img src="assets/img/profile_aman_github.jpeg" alt="" class="img-fluid rounded-circle">
```

### Modify Social Links

Lines 69-70 in header profile section:
```html
<a href="GITHUB_URL" class="twitter" target="_blank"><i class="bx bxl-github"></i></a>
<a href="LINKEDIN_URL" class="linkedin" target="_blank"><i class="bx bxl-linkedin"></i></a>
```

### Update Contact Information

Lines 403-413 in contact section:
- Location (line 406)
- Email (line 412)
- Google Maps embed (line 423)

## Browser Compatibility

Template uses Bootstrap 5, which supports:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

IE11 is not supported.

## License

Template is licensed under BootstrapMade license: https://bootstrapmade.com/license/

## Git Workflow

This repository follows a simple workflow:
- **Main branch**: `master`
- Direct commits to master trigger GitHub Pages deployment
- Include co-author attribution in commits: `Co-Authored-By: Warp <agent@warp.dev>`
