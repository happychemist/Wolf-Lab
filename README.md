# Meridian Biolabs — storefront

Vite + React 19 + Tailwind 4. Static build, no backend.

## Run locally

```bash
npm install
npm run dev          # http://localhost:5173
```

## Build

```bash
npm run build        # outputs to dist/
npm run preview      # serve the production build locally
```

## Deploy

### Cloudflare Pages (recommended here)

```bash
npm install -g wrangler
wrangler login
npm run build
wrangler pages deploy dist --project-name meridian
```

Gives you `meridian.pages.dev` immediately. Add a custom domain under
Workers & Pages → your project → Custom domains.

### Vercel

```bash
npm install -g vercel
vercel            # preview URL
vercel --prod     # production
```

Framework preset auto-detects as Vite. Build command `npm run build`,
output directory `dist`.

### Netlify

```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

Or connect the GitHub repo and set build `npm run build`, publish `dist`.

## Domain

Buy at Cloudflare Registrar (at-cost, no markup) or Namecheap. Point the
apex and `www` at your host per its custom-domain instructions. TLS is
automatic on all three hosts above.

## What this does not include

Cart state lives in React memory and clears on refresh. There is no
checkout, no order storage, no payment processing, and no COA file
serving. Those need a backend — see the notes in chat.

## Before going live

- Replace brand name, favicon, and all placeholder copy.
- Have the conditions-of-sale text reviewed by a regulatory attorney.
- Replace lot codes and COA figures with real analytical data. Publishing
  fabricated certificate values is its own serious problem, separate from
  anything else.
