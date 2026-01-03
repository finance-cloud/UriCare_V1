# UriCare Capsule Landing Page Instructions

## Project Overview
This is a Hindi/English bilingual landing page for UriCare Capsule, an Ayurvedic urinary health supplement. The project consists of three HTML pages with a mobile-first design approach using Tailwind CSS and custom styling.

## Architecture & File Structure
- **[index.html](index.html)** - Main landing page shell (header/footer only, content in test.html)
- **[test.html](test.html)** - Complete product page with all sections (sections are standalone)
- **[ThankYou.html](ThankYou.html)** - Order confirmation page with Facebook Pixel tracking
- **[Image/](Image/)** - Product images, customer testimonials, and medical trust badges

## Key Design Patterns

### Color System
Always use the CSS custom properties defined in `:root`:
```css
--primary: #8B1538;      /* Deep burgundy for headers/CTA */
--secondary: #C85A7A;    /* Medium pink for accents */
--light: #E8A4B8;        /* Light pink for borders */
--background: #FFF0F5;   /* Very light pink background */
--text-dark: #1A1A1A;    /* Main text color */
```

### Typography Strategy
- **[font-eczar](index.html#L30)** - Headlines and product names (serif)
- **[font-yantra](index.html#L35)** - Body text and descriptions (sans-serif)
- Always include Hindi/English bilingual content in product descriptions

### Component Patterns

#### Interactive Elements
- **FAQ Toggle**: Use `.faq-item.active` class with `toggleFAQ(button)` function
- **Trust Cards**: Implement click animations with `animateTrustCard()` for verification badges
- **CTA Buttons**: Golden gradient with hover scaling: `transform hover:scale-105 transition-all duration-300`

#### Section Structure Template
```html
<section id="section-name" class="w-full p-4 relative overflow-hidden" 
         style="background: linear-gradient(135deg, [colors]);">
    <!-- Background decorative elements with animations -->
    <div class="absolute inset-0 opacity-8">...</div>
    
    <div class="max-w-md mx-auto relative z-10">
        <!-- Content here -->
    </div>
</section>
```

#### Mobile Container
All content must use: `<div class="main-container">` (max-width: 450px, centered)

## Content Conventions

### Bilingual Implementation
- Primary text in Hindi with English subtitles
- Product benefits use both languages: "प्राकृतिक मूत्र संबंधी समर्थन" / "Natural Urinary Support"
- Always include English translations for medical terms

### Image References
- Product shots: `./Image/Product.png`, `./Image/Product1.png`
- Customer testimonials: `./Image/Client1.png` through `./Image/Client3.png`
- Trust badges: `./Image/Trust1.png` through `./Image/Trust4.png`
- Problem illustrations: `./Image/Problem1.png` through `./Image/Problem6.png`

## Technical Implementation

### Form Handling
- Form submission uses `showThankYou()` function in [test.html](test.html#L1685)
- Redirects to [ThankYou.html](ThankYou.html) with Facebook Pixel conversion tracking
- Validation requires name and 10-15 digit phone number

### Animation Framework
- Use CSS animations for trust card interactions (ripple effects, scaling)
- FAQ expand/collapse with `max-height` transitions
- Background decorative elements use `animate-pulse`, `animate-bounce`, `animate-ping`

### Responsive Breakpoints
- Mobile-first approach with `max-[450px]:` for small devices
- Use Tailwind responsive prefixes: `md:text-3xl`, `max-[450px]:text-xl`

## Development Workflow

### Adding New Sections
1. Follow the section structure template above
2. Include bilingual content (Hindi primary, English secondary)
3. Add relevant background animations using absolute positioning
4. Ensure mobile responsiveness within `.main-container`
5. Use brand color variables consistently

### Trust/Safety Elements
Always include disclaimer text in footer: "This product is not intended to diagnose, treat, cure, or prevent any disease."

### External Dependencies
- Tailwind CSS via CDN: `@tailwindcss/browser@4`
- Google Fonts: Eczar (serif) and Yantramanav (sans-serif)
- Facebook Pixel for conversion tracking (Thank You page only)

## Common Patterns to Follow
- Gradient backgrounds for sections with 135deg angle
- Trust badges with hover animations and verification states
- Emoji usage for visual appeal: 🌿 (natural), 💪 (strength), ⚡ (energy)
- Price formatting with currency symbols and discount badges
- Medical professional endorsement language in Hindi