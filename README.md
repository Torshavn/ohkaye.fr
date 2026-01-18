# ohkaye.fr

A professional photo portfolio website built with Nuxt 3 and Vue.js.

## Features

- �� Responsive photo gallery with grid layout
- 🖼️ Individual photo pages with details and technical information
- 🎨 Clean, modern design with smooth animations
- 📱 Mobile-friendly responsive design
- ⚡ Fast performance with Nuxt 3
- 🔍 SEO optimized with meta tags

## Tech Stack

- **Framework**: Nuxt 3
- **Frontend**: Vue 3
- **Language**: TypeScript
- **Styling**: CSS (scoped styles)

## Development

### Prerequisites

- Node.js (v16 or higher)
- npm

### Installation

```bash
# Install dependencies
npm install
```

### Running Locally

```bash
# Start development server
npm run dev
```

The site will be available at `http://localhost:3000`

### Building for Production

```bash
# Build the application
npm run build

# Preview production build
npm run preview
```

### Generate Static Site

```bash
# Generate static site
npm run generate
```

## Project Structure

```
├── app.vue              # Root component
├── nuxt.config.ts       # Nuxt configuration
├── layouts/
│   └── default.vue      # Default layout with header and footer
├── pages/
│   ├── index.vue        # Home page with photo gallery
│   ├── about.vue        # About page
│   └── photo/
│       └── [id].vue     # Individual photo page
├── components/
│   └── PhotoGallery.vue # Gallery grid component
└── public/              # Static assets
```

## Customization

### Adding Photos

Edit the `photos` array in:
- `components/PhotoGallery.vue`
- `pages/photo/[id].vue`

Replace the placeholder images with your own photos.

### Styling

All components use scoped CSS. You can customize:
- Colors and fonts in individual components
- Layout in `layouts/default.vue`
- Global styles in `app.vue`

## License

Copyright © 2026 ohkaye.fr
