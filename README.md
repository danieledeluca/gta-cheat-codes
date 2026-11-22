# GTA cheat codes

A web application to browse and search Grand Theft Auto cheat codes with visual controller input guides.

## Features

- **Search & filtering**: real-time cheat code filter by category, effect, and description, synced with the URL query parameters.
- **Visual button inputs**: controller SVG icons (PlayStation / D-pad prompts) rendered for each cheat sequence.
- **Categorized list**: cheats grouped dynamically by category.
- **Theme support**: dark and light mode support via `@nuxt/ui`.
- **Responsive layout**: mobile-friendly UI built with Tailwind CSS.

## Tech Stack

| Layer     | Technology                                                         |
| --------- | ------------------------------------------------------------------ |
| Framework | Nuxt 4, Vue 3, TypeScript                                          |
| UI        | Nuxt UI 4, Tailwind CSS 4, Lucide icons                            |
| Image     | `@nuxt/image`                                                      |
| Quality   | ESLint (`@antfu/eslint-config`), `lint-staged`, `simple-git-hooks` |

## Getting Started

### Prerequisites

- Node.js **20+**
- npm

### Setup

```bash
git clone https://github.com/danieledeluca/gta-cheat-codes.git
cd gta-cheat-codes
npm install
```

```bash
npm run dev          # Start dev server
```

## Scripts

| Command            | Description              |
| ------------------ | ------------------------ |
| `npm run dev`      | Start development server |
| `npm run build`    | Build for production     |
| `npm run preview`  | Preview production build |
| `npm run generate` | Generate static site     |
| `npm run lint`     | Run ESLint               |
| `npm run lint:fix` | Run ESLint with auto-fix |

## Project Structure

```
app/            Nuxt app: pages, components, layouts, assets (JSON cheat database)
public/         Static assets: controller SVG icons and cover images
```

Conventions:

- Cheat code data is stored in `app/assets/cheat-codes/` as structured JSON files.
- Code style is enforced by ESLint (`@antfu/eslint-config`) and pre-commit hooks via `lint-staged`.
