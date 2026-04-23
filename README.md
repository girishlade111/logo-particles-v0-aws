# Logo Particles - Vercel & AWS

An interactive particle animation that forms the Vercel and AWS logos using HTML5 Canvas. Move your mouse or touch to scatter particles and reveal the dual-branding effect.

[![Deployed on Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=for-the-badge&logo=vercel)](https://vercel.com)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-black?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-black?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com)

---

## Overview

This project renders the **Vercel** and **AWS** logos using particle systems on an HTML5 Canvas. Particles are arranged to form the logos and respond to mouse/touch interaction by scattering and revealing color-coded particles.

---

## Features

### Core Features
- **Interactive Particle Animation** - Particles form logos and scatter on mouse/touch proximity
- **Dual-Logo Rendering** - Displays both Vercel and AWS logos simultaneously
- **Responsive Design** - Adapts to any screen size with scaled particle density
- **Touch Support** - Full mobile/tablet support with touch events
- **Color-Coded Particles** - Vercel particles (#00DCFF cyan), AWS particles (#FF9900 orange)
- **Particle Lifecycle** - Particles regenerate over time for dynamic effect
- **Smooth Animations** - 60fps animation with easing transitions back to base position

### Technical Highlights
- Canvas-based rendering for high performance
- Device pixel ratio aware for crisp rendering on retina displays
- Dynamic particle count based on viewport size
- Event-based particle scattering with configurable radius

---

## Tech Stack

| Category | Technology | Version |
|----------|------------|---------|
| **Framework** | Next.js | 15.2.4 |
| **Language** | TypeScript | 5.x |
| **Styling** | Tailwind CSS | 3.4.17 |
| **UI Components** | Radix UI | 1.x |
| **Forms** | React Hook Form + Zod | 7.54 / 3.24 |
| **Fonts** | Geist | 1.3.1 |
| **Analytics** | Vercel Analytics | 1.3.1 |
| **Package Manager** | pnpm | 10.x |

### Key Dependencies
- `@radix-ui/react-*` - Unstyled, accessible UI primitives
- `lucide-react` - Icon library
- `recharts` - Charting library
- `sonner` - Toast notifications
- `clsx` / `tailwind-merge` - Utility class merging

---

## Project Structure

```
logo-particles-v0-aws/
├── app/
│   ├── globals.css       # Global styles & CSS variables
│   ├── layout.tsx       # Root layout with metadata
│   └── page.tsx         # Main page entry
├── components/
│   └── theme-provider.tsx # Theme provider component
├── lib/
│   └── utils.ts          # Utility functions (cn, etc.)
├── vercel-logo-particles.tsx # Main particle animation component
├── aws-logo-path.ts      # AWS logo SVG path data
├── tailwind.config.ts    # Tailwind configuration
├── tsconfig.json        # TypeScript configuration
├── components.json      # shadcn/ui component registry
├── package.json         # Dependencies & scripts
└── pnpm-lock.yaml       # Lock file
```

---

## Getting Started

### Prerequisites
- Node.js 18+ 
- pnpm (recommended) or npm/yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/girishlade111/logo-particles-v0-aws.git
cd logo-particles-v0-aws

# Install dependencies with pnpm
pnpm install

# Or with npm
npm install

# Or with yarn
yarn install
```

### Development

```bash
# Start development server
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start

# Run linting
pnpm lint
```

---

## Configuration

### Environment Variables

Create a `.env.local` file if needed:

```env
# Vercel Analytics (optional)
NEXT_PUBLIC_VERCEL_ANALYTICS_ID=your_analytics_id
```

### Canvas Configuration

Key parameters in `vercel-logo-particles.tsx`:

| Parameter | Default | Description |
|-----------|---------|-------------|
| `baseParticleCount` | 7000 | Base particle count for 1080p |
| `maxDistance` | 240px | Mouse attraction radius |
| `particleGap` | 2 | Gap between particle sampling |
| `easingFactor` | 0.1 | Return animation speed |
| `logoHeight` | 120px (desktop) / 60px (mobile) | Logo rendering size |
| `logoSpacing` | 60px (desktop) / 30px (mobile) | Gap between logos |

### Responsive Breakpoints

- **Mobile**: `< 768px` - Smaller logos, reduced particle count
- **Desktop**: `>= 768px` - Full-size logos, maximum particle density

---

## How It Works

### Particle System
1. **Initialization** - Canvas draws logos to an off-screen buffer
2. **Sampling** - Particles are created at positions where logo pixels exist
3. **Animation Loop** - RequestAnimationFrame updates particle positions
4. **Interaction** - Mouse/touch position calculates distance and applies force
5. **Scattering** - Particles move away from cursor, changing to accent colors
6. **Recovery** - Particles ease back to base positions when cursor leaves

### Color System
- **Base State**: White particles (`#FFFFFF`)
- **Vercel Accent**: Cyan (`#00DCFF`) - applies to Vercel logo particles
- **AWS Accent**: Orange (`#FF9900`) - applies to AWS logo particles

---

## Deployment

### Vercel (Recommended)

1. Push to GitHub
2. Connect repository to [Vercel](https://vercel.com)
3. Deploy automatically on push

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

### Other Platforms

```bash
# Build for static export (if needed)
pnpm build
# Output in .next/static/
```

---

## Statistics

| Metric | Value |
|--------|-------|
| Base Particle Count | ~7,000 |
| Animation FPS | 60 |
| Mouse Interaction Radius | 240px |
| Logo Height (Desktop) | 120px |
| Logo Height (Mobile) | 60px |
| Supported Browsers | All modern browsers |

---

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | Full |
| Firefox 88+ | Full |
| Safari 14+ | Full |
| Edge 90+ | Full |
| Mobile Safari | Full |
| Chrome Mobile | Full |

---

## License

Private project - All rights reserved.

---

## Credits

- Vercel logo path data
- AWS logo path data
- Built with [Next.js](https://nextjs.org)
- Deployed on [Vercel](https://vercel.com)