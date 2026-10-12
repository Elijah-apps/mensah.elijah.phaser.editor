# How to Run Phaser Editor 2D v3

This document provides complete instructions for installing, building, and running the Phaser Editor 2D v3 client.

## Prerequisites

- **Node.js** (version 18+ recommended)
- **npm** (comes with Node.js)
- **Git** (for cloning the repository)
- A modern, updated browser (Chrome, Firefox, Edge, Safari)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/PhaserEditor2D/PhaserEditor2D-v3.git
cd PhaserEditor2D-v3
```

### 2. Switch to Development Branch (Optional)

For the latest in-development changes:

```bash
cd source/editor
git checkout develop
```

### 3. Install Dependencies

```bash
cd source/editor
npm install
```

This installs all required packages (TypeScript, tslint, colibri-packer, etc.).

## Building

### Production Build

```bash
npm run build
```

This runs `tsc -b` (TypeScript compiler in build mode) to compile the client source code.

### Development Build (Watch Mode)

For continuous compilation during development:

```bash
npm start
```

This runs `tsc -b -w` (watch mode) and recompiles on file changes.

### Clean Build

To clean the build output:

```bash
npm run clean
```

This runs `tsc -b -clean`.

## Running the Editor

The client must be served by the Phaser Editor 2D Core server. You have two options:

### Option 1: Using the Launcher (Recommended)

Install and run the launcher:

```bash
npx phasereditor2d-launcher -editor . -dev -disable-plugins phasereditor2d.code -project /path/to/your/game/project
```

**Options explained:**
- `-editor .` - Use the current directory as the client source
- `-dev` - Disable browser cache (always fetch fresh files)
- `-disable-plugins phasereditor2d.code` - Disable the Advanced JavaScript Editor plugin (used in All-in-One, not Core)
- `-project /path/to/game` - **Required**: Path to your Phaser game project

### Option 2: Manual Server Setup

If you have the Phaser Editor 2D Core server installed separately, configure it to serve the client from `source/editor/`.

## Accessing the Editor

Once the server is running, open your browser to:

```
http://127.0.0.1:1959/editor
```

### Important Notes

1. **Clear browser cache** - If you used a previous version, clear your browser cache in Developer Tools before loading
2. **Disable browser cache** - Keep Developer Tools open with "Disable cache" checked (Network tab) during development
3. **Modern browser required** - Use an updated Chrome, Firefox, Edge, or Safari

## Project Structure

```
source/editor/
├── package.json          # NPM configuration
├── tsconfig.json         # TypeScript configuration
├── plugins/              # Editor plugins
├── static/               # Static assets
└── src/                  # Source code (compiled to ./out)
```

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Build fails | Run `npm run clean` then `npm run build` |
| Browser shows old code | Clear cache, use `-dev` flag, disable cache in DevTools |
| Server won't start | Ensure port 1959 is free, check project path exists |
| TypeScript errors | Run `npm run build` to see full error output |

## Useful Commands Summary

```bash
# Full setup from scratch
git clone https://github.com/PhaserEditor2D/PhaserEditor2D-v3.git
cd PhaserEditor2D-v3/source/editor
npm install
npm run build

# Development workflow
npm start                    # Watch mode (terminal 1)
npx phasereditor2d-launcher -editor . -dev -disable-plugins phasereditor2d.code -project /path/to/game  # Terminal 2

# Open browser
# http://127.0.0.1:1959/editor
```

## Documentation & Support

- **Official Documentation**: https://help.phasereditor2d.com
- **Website**: https://phasereditor2d.com
- **Discord**: https://discord.com/invite/4DdpMMD
- **Issues**: https://github.com/PhaserEditor2D/PhaserEditor2D-v3/issues
- **Email**: developers@phasereditor2d.com

## License

MIT License - See LICENSE file for details.