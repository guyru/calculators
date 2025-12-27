# Calculator Development Guidelines

## Design Philosophy

Design should be clean and minimal, focusing on usability. The UI should be responsive and work well on both mobile and desktop devices.

## File Structure

- Each calculator should have its own HTML file
- Common CSS rules should go in `shared.css`
- Keep JavaScript inline within each calculator's HTML file for simplicity

## Design System

### CSS Variables
All styling uses CSS custom properties defined in `:root` in `shared.css`:

**Colors:**
- `--color-bg`: Light gray background (#f8f9fa)
- `--color-surface`: White surface for cards (#ffffff)
- `--color-primary`: Blue accent for interactive elements (#2563eb)
- `--color-primary-hover`: Darker blue for hover states (#1d4ed8)
- `--color-text`: Dark gray for primary text (#1f2937)
- `--color-text-secondary`: Medium gray for secondary text (#6b7280)
- `--color-border`: Light gray for borders (#e5e7eb)
- `--color-border-focus`: Light blue for focus states (#93c5fd)
- `--color-success`: Green for success states (#10b981)
- `--color-error`: Red for error states (#ef4444)

**Spacing Scale:**
- `--spacing-xs`: 0.5rem (8px)
- `--spacing-sm`: 1rem (16px)
- `--spacing-md`: 1.5rem (24px)
- `--spacing-lg`: 2rem (32px)
- `--spacing-xl`: 3rem (48px)

**Border Radius:**
- `--radius-sm`: 0.375rem (6px)
- `--radius-md`: 0.5rem (8px)
- `--radius-lg`: 0.75rem (12px)

### Typography
- Use system font stack for performance and native feel
- Font weights: 700 (headings), 600 (subheadings), 500 (labels), 400 (body)
- Letter-spacing: -0.025em for large text
- Line height: 1.6 for body text, 1.5 for UI elements

## Best Practices

### Styling
- **No inline styles** - All styling should be in CSS files or `<style>` blocks
- Use CSS variables for consistency
- Flat design with subtle borders instead of heavy shadows
- Simple transitions (0.15s ease) for interactive elements

### Accessibility
- Include comprehensive ARIA labels on interactive elements
- Use semantic HTML (`<label>`, `<form>`, `<button>`, etc.)
- Ensure proper focus states with visible outlines
- Include `aria-live` regions for dynamic content
- Use `aria-describedby` for form field hints

### Responsive Design
- Mobile-first approach
- Test on both mobile and desktop
- Use `font-size: 16px` for inputs on mobile to prevent iOS zoom
- Stack form rows vertically on mobile (< 640px)
- Ensure tap targets are at least 44x44px

### SEO & Meta Tags
Each calculator should include:
- Descriptive `<title>` tag
- Meta description (150-160 characters)
- Relevant keywords
- Open Graph tags for social sharing
- Twitter Card tags
- Canonical URL

### Navigation
- Include back link to index: `<a href="index.html" class="back-link">← Back to Calculators</a>`
- Include GitHub links in footer using `.github-links` class
- Consistent link structure across all calculators

### Form Inputs
- Always include `<label>` elements with `for` attributes
- Use appropriate `type`, `min`, `max`, `step` attributes
- Add `.unit-label` or `.help-text` for additional guidance
- Show validation errors clearly
- Calculate results in real-time on input change when possible

### Device Sensors
When using device sensors (orientation, geolocation, etc.):
- Request permissions explicitly with clear UI
- Show permission status and error messages
- Provide fallbacks for unsupported devices
- Handle both standard and vendor-prefixed APIs (e.g., `webkitCompassHeading`)
- Implement appropriate filtering/smoothing for noisy sensor data

## Code Quality
- Keep JavaScript simple and readable
- Comment complex calculations or algorithms
- Include formula sources/references in info boxes
- Handle edge cases and invalid inputs gracefully
- Test thoroughly on multiple devices and browsers
