# Shane Boulos Portfolio

Professional portfolio website built with Astro and deployed on Cloudflare Pages.

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

## Deployment

This site is configured for deployment on Cloudflare Pages:

1. Push your code to GitHub
2. Connect your GitHub repository to Cloudflare Pages
3. Configure build settings:
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Node version: 18 or higher

## Tech Stack

- **Framework**: Astro
- **Styling**: Native CSS with custom properties
- **Font**: Space Mono (Google Fonts)
- **Deployment**: Cloudflare Pages
- **Version Control**: Git/GitHub

## Project Structure

```
/
├── public/           # Static assets
├── src/
│   ├── components/   # Reusable components
│   ├── layouts/      # Page layouts
│   └── pages/        # Route pages
├── astro.config.mjs  # Astro configuration
└── package.json      # Dependencies
```

## Customization

To customize the content:

1. Update personal information in `src/components/Hero.astro`
2. Add/edit projects in `src/components/Projects.astro`
3. Update skills in `src/components/Skills.astro`
4. Modify contact details in `src/components/Contact.astro`

## License

MIT
