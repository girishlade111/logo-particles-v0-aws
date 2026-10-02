# Logo Particles - Vercel & AWS

> An interactive particle animation that forms the **Vercel** and **AWS** logos using HTML5 Canvas. Move your mouse or touch to scatter particles and reveal the dual-branding effect.

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

- **Interactive Particle Animation** — Particles form logos and scatter on mouse/touch proximity
- **Dual-Logo Rendering** — Displays both Vercel and AWS logos simultaneously side by side
- **Responsive Design** — Adapts to any screen size with dynamically scaled particle density
- **Touch Support** — Full mobile/tablet support with touch event handling
- **Color-Coded Particles** — Vercel particles (`#00DCFF` cyan), AWS particles (`#FF9900` orange)
- **Particle Lifecycle** — Particles regenerate over time for continuous dynamic effect
- **Smooth Animations** — 60fps animation with easing transitions back to base positions

### Technical Highlights

- Canvas-based rendering for high performance
- Device pixel ratio aware for crisp rendering on retina/HiDPI displays
- Dynamic particle count based on viewport size
- Event-based particle scattering with configurable radius
- Off-screen canvas buffer for efficient logo pixel sampling
- Particle regeneration system to maintain consistent density

### Visual Effects

- **Base State**: White particles (`#FFFFFF`) forming the logos
- **Vercel Accent**: Cyan (`#00DCFF`) particles when scattered
- **AWS Accent**: Orange (`#FF9900`) particles when scattered
- **Force-based scattering**: Particles repel from cursor based on proximity
- **Easing recovery**: Particles smoothly return to original positions

---

## Tech Stack

### Production Dependencies

| Category | Technology | Version |
|----------|------------|---------|
| **Framework** | Next.js | 15.2.4 |
| **Language** | TypeScript | 5.x |
| **Styling** | Tailwind CSS | 3.4.17 |
| **UI Components** | Radix UI | 1.x |
| **Forms** | React Hook Form + Zod | 7.54 / 3.24 |
| **Fonts** | Geist | 1.3.1 |
| **Analytics** | Vercel Analytics | 1.3.1 |
| **Icons** | Lucide React | 0.454.0 |
| **Charts** | Recharts | 2.15.0 |
| **Notifications** | Sonner | 1.7.1 |
| **Carousel** | Embla Carousel | 8.5.1 |
| **Package Manager** | pnpm | 10.x |

### Development Dependencies

| Category | Technology | Version |
|----------|------------|---------|
| **Type Definitions** | @types/node, @types/react | 22 / 19 |
| **PostCSS** | PostCSS + Autoprefixer | 8.5 / 10.4 |
| **Type Checking** | TypeScript | 5.x |

### Radix UI Components Used

- `@radix-ui/react-accordion` — Accordion components
- `@radix-ui/react-dialog` — Modal dialogs
- `@radix-ui/react-dropdown-menu` — Dropdown menus
- `@radix-ui/react-select` — Select dropdowns
- `@radix-ui/react-tabs` — Tab navigation
- `@radix-ui/react-tooltip` — Tooltips
- `@radix-ui/react-slider` — Slider inputs
- `@radix-ui/react-switch` — Toggle switches
- `@radix-ui/react-checkbox` — Checkbox inputs
- `@radix-ui/react-toast` — Toast notifications
- `@radix-ui/react-progress` — Progress bars
- `@radix-ui/react-avatar` — Avatar components

---

## Project Structure

```
logo-particles-v0-aws/
├── app/
│   ├── globals.css           # Global styles, CSS variables & Tailwind directives
│   ├── layout.tsx           # Root layout with metadata & fonts
│   └── page.tsx             # Main page entry point
├── components/
│   └── theme-provider.tsx    # Theme provider for dark mode support
├── lib/
│   └── utils.ts              # Utility functions (cn, class merging)
├── styles/
│   └── globals.css           # Additional global styles
├── public/
│   ├── placeholder.svg       # Placeholder images
│   ├── placeholder.jpg
│   ├── placeholder-user.jpg
│   ├── placeholder-logo.svg
│   └── placeholder-logo.png
├── vercel-logo-particles.tsx # Main particle animation component
├── aws-logo-path.ts          # AWS logo SVG path data
├── tailwind.config.ts        # Tailwind CSS configuration
├── next.config.mjs           # Next.js configuration
├── postcss.config.mjs        # PostCSS configuration
├── tsconfig.json            # TypeScript configuration
├── components.json           # shadcn/ui component registry
├── package.json             # Dependencies & scripts
└── pnpm-lock.yaml           # Lock file
```

---

## Getting Started

### Prerequisites

- **Node.js**: Version 18 or higher
- **Package Manager**: pnpm (recommended), npm, or yarn

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

### Development Commands

```bash
# Start development server with hot reload
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start

# Run ESLint
pnpm lint
```

### Development Server

The development server runs on `http://localhost:3000` by default. The application will automatically reload when you make changes to the code.

---

## Configuration

### Environment Variables

Create a `.env.local` file in the root directory if needed:

```env
# Vercel Analytics (optional)
NEXT_PUBLIC_VERCEL_ANALYTICS_ID=your_analytics_id
```

### Next.js Configuration (`next.config.mjs`)

```javascript
{
  eslint: {
    ignoreDuringBuilds: true,   // Skip ESLint during builds
  },
  typescript: {
    ignoreBuildErrors: true,    // Skip TypeScript errors during builds
  },
  images: {
    unoptimized: true,          // Disable image optimization
  },
}
```

### Tailwind Configuration (`tailwind.config.ts`)

- **Dark Mode**: Enabled via `class` strategy
- **Content Paths**: Pages, components, and app directories
- **Custom Colors**: HSL-based color system with CSS variables
- **Custom Animations**: Accordion open/close animations
- **Plugins**: `tailwindcss-animate` for enhanced animations

### Canvas Configuration

Key parameters in `vercel-logo-particles.tsx`:

| Parameter | Default | Description |
|-----------|---------|-------------|
| `baseParticleCount` | 7000 | Base particle count for 1080p displays |
| `maxDistance` | 240px | Mouse attraction/scatter radius |
| `particleGap` | 2 | Gap between particle sampling points |
| `easingFactor` | 0.1 | Return animation speed (lerp factor) |
| `logoHeight` | 120px (desktop) / 60px (mobile) | Logo rendering height |
| `logoSpacing` | 60px (desktop) / 30px (mobile) | Gap between logos |
| `particleSize` | 0.5 - 1.5px | Random particle size range |
| `particleLife` | 50 - 150 frames | Particle lifespan before regeneration |

### Responsive Breakpoints

| Breakpoint | Screen Width | Logo Height | Logo Spacing | Particle Density |
|------------|--------------|-------------|-------------|------------------|
| **Mobile** | `< 768px` | 60px | 30px | 50% of desktop |
| **Desktop** | `>= 768px` | 120px | 60px | 100% (full density) |

---

## How It Works

### Particle System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    PARTICLE SYSTEM FLOW                     │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  1. INITIALIZATION                                           │
│     ├── Create off-screen canvas                             │
│     ├── Draw Vercel logo path                                │
│     ├── Draw AWS logo path                                   │
│     └── Capture ImageData pixels                            │
│                                                              │
│  2. PARTICLE CREATION                                        │
│     ├── Sample pixel positions where logo exists             │
│     ├── Create particle at each valid position               │
│     ├── Assign base position and scattered color             │
│     └── Set random particle properties (size, life)           │
│                                                              │
│  3. ANIMATION LOOP (60fps)                                   │
│     ├── Clear canvas                                         │
│     ├── Fill background with black                           │
│     ├── For each particle:                                    │
│     │   ├── Calculate distance to mouse cursor               │
│     │   ├── If within scatter radius → move away + accent color│
│     │   └── If outside → ease back to base position          │
│     └── Render particles to canvas                            │
│                                                              │
│  4. PARTICLE REGENERATION                                    │
│     ├── Decrement particle life                              │
│     ├── When life <= 0 → replace with new particle            │
│     └── Maintain target particle count                        │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### Logo Rendering

- **Vercel Logo**: Drawn using bezier curves and line paths
- **AWS Logo**: Rendered using SVG path data via `Path2D`
- Both logos maintain aspect ratios during scaling
- Logos are positioned side by side with configurable spacing

### Interaction Flow

```
Mouse/Touch Input
       │
       ▼
Calculate Distance to Each Particle
       │
       ▼
┌──────────────────┐
│ Distance < 240px │
└────────┬─────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Calculate scatter force            │
│  force = (maxDistance - distance) / maxDistance │
└─────────────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Move particle opposite to cursor   │
│  newX = baseX - cos(angle) * force * 60│
│  newY = baseY - sin(angle) * force * 60│
│  Apply scattered color (#00DCFF / #FF9900)│
└─────────────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  When cursor leaves:                │
│  Ease particle back to baseX/baseY  │
│  x += (baseX - x) * 0.1             │
│  y += (baseY - y) * 0.1             │
│  Reset color to white                │
└─────────────────────────────────────┘
```

### Color System

| State | Vercel Particles | AWS Particles | Description |
|-------|-----------------|---------------|-------------|
| **Base** | White (`#FFFFFF`) | White (`#FFFFFF`) | Logo shape formed |
| **Scattered** | Cyan (`#00DCFF`) | Orange (`#FF9900`) | When cursor nearby |

---

## Statistics

| Metric | Value | Notes |
|--------|-------|-------|
| **Base Particle Count** | ~7,000 | For 1920x1080 display |
| **Animation FPS** | 60 | Smooth 60 frames per second |
| **Mouse Interaction Radius** | 240px | Maximum scatter distance |
| **Logo Height (Desktop)** | 120px | Full-size logos |
| **Logo Height (Mobile)** | 60px | Compact mobile view |
| **Particle Size Range** | 0.5 - 1.5px | Randomized for natural look |
| **Particle Lifespan** | 50 - 150 frames | Regeneration cycle |
| **Easing Factor** | 0.1 | Smooth return animation |
| **Responsive Scaling** | √(viewport/1080p) | Density adjustment |
| **Supported Browsers** | All modern browsers | Chrome, Firefox, Safari, Edge |

---

## Deployment

### Deploy to Vercel (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "feat: logo particles"
   git push origin main
   ```

2. **Connect to Vercel**
   - Go to [vercel.com/new](https://vercel.com/new)
   - Import your GitHub repository
   - Vercel will automatically detect Next.js configuration

3. **Deploy**
   - Click "Deploy"
   - Your site will be live at `https://your-project.vercel.app`

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

### Manual Build

```bash
# Build for production
pnpm build

# The output will be in .next/static/
# Preview locally before deploying
pnpm start
```

### Deploy to Other Platforms

For static export or other hosting providers:

```bash
# Create output directory
mkdir -p out

# Note: Next.js 15 may require additional config for static export
# Check Next.js documentation for export options
```

---

## Browser Support

| Browser | Version | Support | Notes |
|---------|---------|---------|-------|
| **Chrome** | 90+ | Full | Primary tested |
| **Firefox** | 88+ | Full | Primary tested |
| **Safari** | 14+ | Full | macOS & iOS |
| **Edge** | 90+ | Full | Chromium-based |
| **Mobile Safari** | iOS 14+ | Full | Touch events |
| **Chrome Mobile** | Android 10+ | Full | Touch events |
| **Samsung Internet** | Latest | Full | Touch events |

### Required APIs

- **Canvas API** — For rendering particles
- **RequestAnimationFrame** — For smooth 60fps animation
- **Touch Events** — For mobile interaction
- **Device Pixel Ratio** — For HiDPI/retina displays

---

## Customization

### Adding Custom Logos

Modify `vercel-logo-particles.tsx` to add different logos:

```typescript
// Example: Adding a custom logo
ctx.save()
ctx.translate(offsetX, offsetY)
ctx.scale(customScale, customScale)
// Draw your custom path here
ctx.fill()
ctx.restore()
```

### Adjusting Particle Behavior

```typescript
// Modify scatter force
const force = (maxDistance - distance) / maxDistance

// Adjust return speed
p.x += (p.baseX - p.x) * 0.15  // Increase for faster return

// Change scatter distance
const maxDistance = 300  // Increase for larger interaction area
```

### Color Customization

```typescript
// Vercel accent color (default: #00DCFF)
scatteredColor: isAWSLogo ? '#FF9900' : '#00DCFF'

// AWS accent color (default: #FF9900)
scatteredColor: isAWSLogo ? '#FF9900' : '#00DCFF'

// Background color (default: black)
ctx.fillStyle = 'black'
```

---

## Connect With Me

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/girish_lade_/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/girish-lade-075bba201/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/girishlade111)
[![CodePen](https://img.shields.io/badge/CodePen-000000?style=for-the-badge&logo=codepen&logoColor=white)](https://codepen.io/Girish-Lade-the-looper)
[![Gmail](https://img.shields.io/badge/Gmail-D44638?style=for-the-badge&logo=gmail&logoColor=white)](mailto:admin@ladestack.in)
[![Website](https://img.shields.io/badge/Website-000000?style=for-the-badge&logo=google-chrome&logoColor=white)](https://ladestack.in)

---

## License

Private project — All rights reserved.

---

## Credits

- Vercel logo path data and brand identity
- AWS logo path data and brand identity
- Built with [Next.js](https://nextjs.org)
- Styled with [Tailwind CSS](https://tailwindcss.com)
- UI components from [Radix UI](https://www.radix-ui.com)
- Deployed on [Vercel](https://vercel.com)
---

**Built by Girish Lade** — [ladestack.in](https://ladestack.in)
