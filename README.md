# Shane Boulos Portfolio

Clean, editorial-style professional portfolio built with Astro and deployed on Cloudflare Pages.

## Design Philosophy

This portfolio uses a minimal, single-column layout inspired by Apple case studies, Medium articles, and Notion's marketing site. Key features:

- **Editorial layout**: Single-column content (680px max width)
- **Generous whitespace**: Content breathes, no clutter
- **Typography-focused**: Space Mono typeface throughout
- **Clean navigation**: Just Work, About, Contact

## Getting Started

### Prerequisites
- Node.js v18 or higher
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

The site will be available at `http://localhost:4321`

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## Project Structure

```
/
├── public/
│   ├── favicon.svg
│   └── images/              # Add your images here
├── src/
│   ├── layouts/
│   │   └── Layout.astro     # Main layout with design system
│   └── pages/
│       ├── index.astro      # Homepage (minimal intro)
│       ├── work.astro       # Work overview
│       ├── about.astro      # About page
│       ├── contact.astro    # Contact page
│       └── work/
│           └── awj.astro    # AWJ case study
├── astro.config.mjs         # Astro configuration
├── package.json             # Dependencies
└── REDESIGN_NOTES.md        # Detailed customization guide
```

## Customization

See `REDESIGN_NOTES.md` for comprehensive customization instructions.

### Quick Updates

**Update content:**
- Homepage intro: `src/pages/index.astro`
- AWJ case study: `src/pages/work/awj.astro`
- About bio: `src/pages/about.astro`
- Contact info: `src/pages/contact.astro`

**Add professional photo:**
1. Add image to `/public/images/profile.jpg`
2. Update `src/pages/about.astro` to use the image

**Adjust design:**
- Colors: Edit CSS variables in `src/layouts/Layout.astro`
- Spacing: Adjust spacing scale in Layout.astro `:root`
- Typography: Modify font sizes and line heights

## Site Pages

- **Homepage** (`/`) - Minimal intro with positioning statement
- **Work** (`/work`) - Overview of case studies
- **AWJ Case Study** (`/work/awj`) - Full editorial narrative with metrics
- **About** (`/about`) - Professional bio and expertise
- **Contact** (`/contact`) - Contact information and availability

## Deployment

### Cloudflare Pages

1. Push your code to GitHub
2. Connect your GitHub repository to Cloudflare Pages
3. Configure build settings:
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Node version: 18 or higher
   - Environment variable: `NODE_VERSION=18`

See `SETUP_GUIDE.md` for detailed deployment instructions.

## Tech Stack

- **Framework**: Astro 4.x
- **Styling**: Native CSS with custom properties (no frameworks)
- **Typography**: Space Mono (Google Fonts)
- **Deployment**: Cloudflare Pages
- **Version Control**: Git/GitHub

## Design System

### Colors
- Background: `#ffffff`
- Text: `#0a0a0a`
- Text (light): `#6b7280`
- Accent: `#2563eb`
- Border: `#e5e7eb`

### Spacing Scale
- XS: 0.75rem (12px)
- SM: 1.5rem (24px)
- MD: 3rem (48px)
- LG: 6rem (96px)
- XL: 9rem (144px)
- 2XL: 12rem (192px)

### Container Widths
- Standard: 680px
- Narrow: 560px

## Development Notes

### Old Components
The `src/components/` folder contains old component files from the previous design. These are no longer used but couldn't be auto-deleted due to permissions. You can safely delete this folder:

```bash
rm -rf src/components/
```

## License

MIT
