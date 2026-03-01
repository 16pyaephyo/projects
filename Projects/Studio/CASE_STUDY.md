# Wedding Photo Studio Project Case Study

## Project: Lumière Studio Website

### Description
A **responsive wedding photography website** built with HTML and CSS.  
The site includes a hero section, about, gallery, services, contact form, and footer.  
Focus is on a clean, timeless aesthetic and smooth user experience across devices.

---

## Problem-Solving Process
- Define project goal: Build a responsive website showcasing photography services.
- Plan layout: Hero section with layered image effect, about section, gallery grid, services, contact form, and footer.
- Implement responsive design:
  - Use CSS grid and flexbox for layout
  - Media queries for tablets and mobile
  - Adjust image sizes, spacing, and typography for different screen widths
- Enhance UX:
  - Clear navigation menu
  - Call-to-action buttons
  - Consistent spacing and visual hierarchy
- Test edge cases:
  - Ensure gallery images scale properly
  - Hero image layering maintains 3D effect
  - Services and contact sections remain readable on small screens

---

## UI/UX Decisions
- **Hero section layered background**: Adds depth and visual interest
- **Typography hierarchy**: Clear headings and readable body text
- **Consistent spacing and padding**: Clean, elegant layout
- **Call-to-action buttons**: Highlight “Book a Session” to guide users
- **Gallery grid**: Flexible layout for different screen sizes
- **Service cards**: Easy-to-read description of offerings
- **Contact form**: Simple, minimal, with clear input fields and button
- **Color palette**: Soft, neutral tones to match wedding aesthetic

---

## CSS / Responsive Design Strategies
| Problem | Solution |
|---------|---------|
| Hero image and background layer overlap on small screens | Used media queries to adjust size and position (`max-width: 768px`) |
| Navigation links too close on mobile | Adjusted flex gap and text size using media queries |
| Gallery images stretched or misaligned | Used `object-fit: cover` and CSS grid for responsive layout |
| Service cards cramped on mobile | Changed grid to 1 column for screens < 768px |
| Contact form not fitting on small devices | Limited form width and adjusted padding/margin for mobile screens |

---

## Before & After Example (CSS snippets)

**Before (desktop-only hero grid)**
```css
.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}
```
**After (responsive for tablet and mobile)**
```css
@media (max-width: 768px) {
  .hero-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
}
```
**Before (gallery images stretched)**
```css
.gallery-grid img {
  width: 100%;
  height: auto;
}
```
**After (maintain aspect ratio)**
```css
.gallery-grid img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```
**Before (service cards in one row only)**
```css
.service-grid {
  display: grid;
  grid-template-columns: repeat(3,1fr);
  gap: 40px;
}
```
**After (responsive)**
```css
@media (max-width: 768px){
  .service-grid {
    grid-template-columns: 1fr;
    gap: 24px;
  }
}
```

## Key Learning Points

- Planning responsive layouts with CSS grid and flexbox
- Using media queries to adapt for mobile and tablet
- Maintaining visual hierarchy and spacing for readability
- Layering images for hero section depth effect
- Ensuring gallery images remain proportionate using object-fit: cover
- Styling a clean, user-friendly contact form
- Thinking ahead about mobile-first and cross-device UX