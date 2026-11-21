# Scenes Tours Admin

Separate, static admin for the main [Scenes Tours & Travels](https://github.com/shema-k/scenes-tours) website.

## What it does

- Connects to the main website repo via GitHub API using a fine-grained Personal Access Token.
- Edits `data.js` content: trips, media references, site details, home/hero/places/legal, services, ways, destinations, FAQ, guides, trip news, team, story/stats, reviews, and published data.
- Uploads and deletes media files in the main website repo.
- Publishes by committing updated `data.js` to the main repo.

## Setup

1. Create a GitHub fine-grained PAT with **Contents: Read and write** on `shema-k/scenes-tours` only. Use a short expiration.
2. Host this repo separately (GitHub Pages/Netlify). Do not put it in the main public website repo.
3. Open the admin, enter token/owner/repo/branch, connect.

## Security

- This is a **static admin**. No server-side auth is included. The page is useless without a valid GitHub token, but the page itself is public unless you protect it.
- For real security, put it behind **Cloudflare Access**, **Netlify/Vercel password/team auth**, or a private VPN.
- Use a fine-grained token scoped to the single main repo, short expiry, private device. Do not commit tokens.
- The admin parses `data.js` by executing it in-browser; only use it against your own trusted repo.
