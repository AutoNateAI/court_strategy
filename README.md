# Autonate AI Documentation Site

AI-powered tools and workshops for families, researchers, and communities using Obsidian and Cursor.

## Project Structure

```
court_strategy/
├── notes/                      # Obsidian notes for planning (not deployed)
├── home.mdx                    # Landing page
├── workshops/                  # Workshop documentation
│   ├── overview.mdx
│   ├── getting-started.mdx
│   └── live-sessions.mdx
├── obsidian-guide/            # Obsidian tutorials
│   ├── introduction.mdx
│   ├── installation.mdx
│   ├── vault-setup.mdx
│   ├── plugins.mdx
│   └── civic-research.mdx
├── cursor-guide/              # Cursor AI tutorials
│   ├── introduction.mdx
│   ├── installation.mdx
│   ├── obsidian-integration.mdx
│   ├── prompts.mdx
│   └── canvas-creation.mdx
├── resources/                 # Additional resources
│   ├── stories.mdx
│   ├── tools.mdx
│   ├── community.mdx
│   └── faq.mdx
├── public/                    # Static assets
│   └── images/
├── mint.json                  # Mintlify configuration
└── package.json              # Dependencies
```

## Getting Started

### Prerequisites

- Node.js 18+ installed
- npm or yarn package manager

### Local Development

1. **Install Mintlify CLI:**
   ```bash
   npm install -g mintlify
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run development server:**
   ```bash
   mintlify dev
   ```

4. **Open in browser:**
   Navigate to `http://localhost:3000`

The dev server will auto-reload when you edit MDX files.

## Deployment

This site is configured to deploy to Vercel automatically via GitHub Actions.

### Initial Setup

1. **Create Vercel Project:**
   - Go to [vercel.com](https://vercel.com)
   - Import this repository
   - Framework Preset: Other
   - Build Command: `mintlify build`
   - Output Directory: `_build`

2. **Get Vercel Credentials:**
   - Install Vercel CLI: `npm i -g vercel`
   - Run `vercel` in project directory
   - Copy the `.vercel/project.json` values:
     - `orgId` → `VERCEL_ORG_ID`
     - `projectId` → `VERCEL_PROJECT_ID`
   - Get token from [vercel.com/account/tokens](https://vercel.com/account/tokens) → `VERCEL_TOKEN`

3. **Add GitHub Secrets:**
   - Go to repository Settings → Secrets and variables → Actions
   - Add three secrets:
     - `VERCEL_TOKEN`
     - `VERCEL_ORG_ID`
     - `VERCEL_PROJECT_ID`

4. **Push to main branch:**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

GitHub Actions will automatically build and deploy your site!

### Manual Deployment (Alternative)

If you prefer manual deployment:

```bash
# Build the site
mintlify build

# Deploy to Vercel
vercel --prod
```

## Content Workflow

### From Notes to Content

The `notes/` folder is your Obsidian workspace for planning and drafting. When ready to publish:

1. **Plan in Obsidian:**
   - Use `notes/` folder as your Obsidian vault
   - Draft content, organize ideas, research

2. **Convert to MDX:**
   - Copy content from `notes/` to appropriate content folder
   - Convert to MDX format (usually minimal changes needed)
   - Add frontmatter (title, description)
   - Add Mintlify components if needed

3. **Update Navigation:**
   - Edit `mint.json` to add new pages to navigation
   - Add to appropriate "pages" array

4. **Test Locally:**
   ```bash
   mintlify dev
   ```

5. **Commit and Push:**
   ```bash
   git add .
   git commit -m "Add new content"
   git push
   ```

GitHub Actions will deploy automatically!

### MDX Frontmatter

Every MDX file should have frontmatter:

```markdown
---
title: Page Title
description: Brief description for SEO
---

# Page content starts here
```

### Mintlify Components

Mintlify provides special components for better documentation:

```markdown
<Card title="Card Title" icon="icon-name" href="/link">
  Card content
</Card>

<CardGroup cols={2}>
  <Card>...</Card>
  <Card>...</Card>
</CardGroup>

<Accordion title="Click to expand">
  Hidden content
</Accordion>

<Tabs>
  <Tab title="Tab 1">Content 1</Tab>
  <Tab title="Tab 2">Content 2</Tab>
</Tabs>

<Steps>
  <Step title="Step 1">Instructions</Step>
  <Step title="Step 2">More instructions</Step>
</Steps>

<Note>Important note</Note>
<Tip>Helpful tip</Tip>
<Warning>Warning message</Warning>
<Info>Information callout</Info>
```

See [Mintlify docs](https://mintlify.com/docs/content/components/card) for full component list.

## Configuration

### Mint.json

The `mint.json` file controls:

- Site name and branding
- Navigation structure
- Color scheme
- Logo and favicon
- Analytics
- Social links

Edit this file to customize your site's structure and appearance.

### Customizing Theme

In `mint.json`, you can customize:

```json
{
  "colors": {
    "primary": "#6366F1",    // Main brand color
    "light": "#818CF8",      // Light variant
    "dark": "#4F46E5"        // Dark variant
  }
}
```

## Adding Images

1. **Add image files to:**
   ```
   public/images/your-image.png
   ```

2. **Reference in MDX:**
   ```markdown
   ![Alt text](/public/images/your-image.png)
   
   # Or with Mintlify image component:
   <img src="/public/images/your-image.png" alt="Alt text" />
   ```

## Troubleshooting

### Dev server won't start

```bash
# Clear cache
rm -rf .mintlify _build

# Reinstall
npm install -g mintlify

# Try again
mintlify dev
```

### Build fails

- Check `mint.json` for JSON syntax errors
- Verify all referenced files exist
- Check frontmatter in MDX files

### Deployment fails

- Check GitHub Actions logs
- Verify Vercel secrets are set correctly
- Ensure `mint.json` is valid

## Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [Mintlify Components](https://mintlify.com/docs/content/components)
- [MDX Documentation](https://mdxjs.com/)
- [Vercel Documentation](https://vercel.com/docs)

## Support

- **Email:** hello@autonateai.com
- **Community:** [Join our community](/resources/community)
- **Workshops:** [View schedule](/workshops/overview)

## License

Content: All rights reserved
Code/Configuration: MIT License

---

Built with [Mintlify](https://mintlify.com)

