# Images Needed for Autonate AI Site

This directory needs the following images to complete the site design:

## Required Images

### Homepage Images (Priority: HIGH)
1. **`obsidian-screenshot.png`** (1200x800px recommended)
   - Screenshot of Obsidian showing:
     - Graph view with connected notes, OR
     - Clean vault with organized folders and notes
     - Should show the power of knowledge connections
   
2. **`cursor-screenshot.png`** (1200x800px recommended)
   - Screenshot of Cursor AI showing:
     - AI chat panel with helpful response
     - Code/markdown editing with AI suggestions
     - Shows the AI-powered workflow

### Guide Page Images (Priority: MEDIUM)
3. **`obsidian-graph.png`** (800x600px recommended)
   - Already referenced in `/obsidian-guide/introduction.mdx`
   - Graph view visualization showing note connections
   
4. **`cursor-interface.png`** (800x600px recommended)
   - Already referenced in `/cursor-guide/introduction.mdx`
   - Full Cursor interface showing AI features
   
5. **`canvas-example.png`** (800x600px recommended)
   - Already referenced in `/cursor-guide/canvas-creation.mdx`
   - Example of an Obsidian canvas with nodes and connections

### Branding Images (Priority: LOW - Can wait)
6. **`logo-light.svg`** - Your logo for light mode
7. **`logo-dark.svg`** - Your logo for dark mode  
8. **`favicon.png`** - Browser tab icon

## How to Get These Images

### Option 1: Take Your Own Screenshots (RECOMMENDED)

**For Obsidian:**
```bash
# 1. Open Obsidian on your computer
# 2. Set up a nice example vault or use your existing one
# 3. For graph view: Open Command Palette (Cmd/Ctrl+P) → "Open graph view"
# 4. Take screenshot (Cmd+Shift+4 on Mac, Windows+Shift+S on Windows)
# 5. Save as obsidian-screenshot.png
```

**For Cursor:**
```bash
# 1. Open Cursor with an Obsidian vault folder
# 2. Open AI chat (Cmd/Ctrl+L)
# 3. Show a helpful AI conversation about research or automation
# 4. Take screenshot showing the full interface
# 5. Save as cursor-screenshot.png
```

### Option 2: Use Official Marketing Images

- **Obsidian**: Visit https://obsidian.md and check their marketing materials
- **Cursor**: Visit https://cursor.sh and check their screenshots

### Option 3: Temporary Placeholders

If you want to launch now and add real screenshots later, you can use:
- Placeholder images from https://placehold.co/1200x800
- Or just remove the image tags temporarily

## Where to Put Images

Save all images in this directory:
```
/Users/nathan.baker/code/court_strategy/public/images/
```

## After Adding Images

1. Commit the images:
   ```bash
   git add public/images/
   git commit -m "Add screenshots for homepage and guides"
   git push origin main
   ```

2. Mintlify will auto-deploy and your images will appear!

## Image Optimization Tips

- **Format**: PNG for screenshots (best quality), JPEG for photos
- **Size**: Keep under 500KB each for fast loading
- **Dimensions**: 1200x800px for featured images, 800x600px for guide images
- **Compression**: Use https://tinypng.com to compress before uploading

## Testing

After adding images, test locally:
```bash
mintlify dev
```

Visit http://localhost:3000 to see your images in action!

