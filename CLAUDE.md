# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**TambakAI** is an AI-powered shrimp farm feeding control system (Sistem Kontrol Pemberian Makan Pada Tambak Udang). The application helps shrimp farm owners optimize feed quantity and timing to improve harvest quality and yields.

### Target Users
Shrimp farm owners (petambak udang) who need daily feeding recommendations.

### Core Functionality
- **Inputs (Sensor Data)**: pH levels, water temperature, weather conditions, shrimp count, water volume
- **Outputs (Actuators/Recommendations)**: Feed quantity (kg), feeding schedules, based on shrimp species, age, size, and survival rates

### AI Method: Sugeno Fuzzy Logic
The system uses the **Sugeno method** (Sugeno-type fuzzy inference system) to determine optimal feed quantities. This approach:
- Uses fuzzy rules to map sensor inputs to feeding recommendations
- Outputs constant or linear functions (rather than fuzzy sets like Mamdani)
- Well-suited for real-time control systems and optimization problems
- Processes multiple input variables (pH, temperature, weather, shrimp count, volume) to calculate precise feed quantities

### Knowledge Base Domain
- Daily shrimp farmer feeding routines
- Pellet quantities in kilograms per feeding
- Feeding timing schedules
- Pond size considerations

## Commands

```bash
# Development
npm run dev          # Start dev server at http://localhost:3000

# Production
npm run build        # Build for production
npm start            # Start production server

# Code Quality
npm run lint         # Run ESLint
```

## Architecture

### Tech Stack
- **Framework**: Next.js 16.2.7 (App Router)
- **React**: 19.2.4
- **React Compiler**: Enabled via `babel-plugin-react-compiler`
- **Language**: JavaScript with path aliases via jsconfig.json

### Project Structure
```
src/
└── app/              # Next.js App Router directory
    ├── layout.js     # Root layout with Geist fonts
    ├── page.js       # Home page
    ├── globals.css   # Global styles
    └── *.module.css  # CSS Modules per component
public/               # Static assets
```

### Key Configuration

**Path Aliases** (`jsconfig.json`):
```js
"@/*" → "./src/*"
```

**React Compiler** (`next.config.mjs`):
- Enabled via `reactCompiler: true`
- Automatic optimizations for React components

### Next.js Version Notes

This project uses Next.js 16.x which may have breaking changes from older versions. Always consult the relevant guide in `node_modules/next/dist/docs/` before writing code, as APIs, conventions, and file structures may differ from training data.

## Development Notes

- The project is in early development stage - currently using the default create-next-app template
- All code uses JavaScript (not TypeScript)
- Component-level styling uses CSS Modules (`*.module.css`)
- ESLint is configured with Next.js core-web-vitals preset
