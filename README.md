# Dembrandt Landing Page

Sleek Silicon Valley-style landing page for [Dembrandt](https://dembrandt.com) - the design system extraction tool.

## Tech Stack

- **Parcel** - Zero-config bundler
- **Tailwind CSS** - Utility-first styling
- **GitHub Pages** - Static site hosting
- **Gandi DNS** - Custom domain management

## Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev
```

Visit `http://localhost:1234`

## Build

```bash
npm run build
```

Output goes to `dist/` folder.

## Deployment

### GitHub Pages

1. **Enable GitHub Pages** in your repo settings:
   - Go to Settings > Pages
   - Source: "GitHub Actions"

2. **Push to main branch** - The GitHub Action will automatically:
   - Build the site
   - Deploy to GitHub Pages
   - Available at `https://dembrandt.github.io/dembrandt.com`

### Gandi DNS Configuration

To use your custom domain `dembrandt.com`:

1. **In GitHub repo settings** (Settings > Pages):
   - Custom domain: `dembrandt.com`
   - Enforce HTTPS: ✓

2. **In Gandi DNS settings**:

   Add these DNS records:

   ```
   Type    Name    Value
   A       @       185.199.108.153
   A       @       185.199.109.153
   A       @       185.199.110.153
   A       @       185.199.111.153
   CNAME   www     dembrandt.github.io.
   ```

3. **Wait for DNS propagation** (can take up to 24 hours, usually faster)

4. **Verify** at https://dembrandt.com

### Alternative: Custom Subdomain

If using a subdomain like `www.dembrandt.com`:

```
Type    Name    Value
CNAME   www     dembrandt.github.io.
```

Update `src/CNAME` to:
```
www.dembrandt.com
```

## Project Structure

```
dembrandt.com/
├── src/
│   ├── index.html          # Main landing page
│   ├── styles.css          # Tailwind + custom styles
│   └── CNAME               # Custom domain config
├── .github/
│   └── workflows/
│       └── deploy.yml      # Auto-deploy on push
├── package.json
├── tailwind.config.js
└── postcss.config.js
```

## Customization

### Colors

Edit `tailwind.config.js` to change brand colors:

```js
colors: {
  brand: {
    500: '#0ea5e9',  // Primary brand color
    // ... other shades
  },
}
```

### Content

Edit `src/index.html` to update:
- Hero text
- Features
- Links to GitHub/npm
- Call-to-action buttons

### Domain

Update `src/CNAME` with your domain:
```
yourdomain.com
```

## License

MIT
