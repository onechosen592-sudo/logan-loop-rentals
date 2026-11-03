# Logan Loop Rentals website

Single static page for a contactless car rental business. No build step.

## Files
- `index.html` is the live site (warm cream design). All CSS and JS are inline.
- `versions/black.html` is the black, olive and orange design, kept as a backup.
- `.nojekyll` makes GitHub Pages serve files as-is.

## Publishing (GitHub Pages)
- GitHub Pages serves the `gh-pages` branch. Live address: https://onechosen592-sudo.github.io/logan-loop-rentals/
- To publish: commit to `main`, then run `git push origin main && git push origin main:gh-pages`.
- Check the deploy: `curl -s https://api.github.com/repos/onechosen592-sudo/logan-loop-rentals/actions/runs?per_page=1` until `pages build and deployment` is `completed success`. github.io itself can't be fetched from the Claude workspace.
- Custom domain: loganlooprentals.com (registered at GoDaddy). Add a `CNAME` file containing `loganlooprentals.com` only after the GoDaddy DNS records point to GitHub Pages, or the github.io address will redirect to a domain that doesn't resolve yet.

## Site settings to fill in
In the script near the top, `var SITE = { stripeLink, idLink, applyEmail }` holds the Stripe payment link, the ID verification link and the driver application email. All are empty until the owner provides them.

## Known limits
Bookings, listings, check-ins, mileage and alerts are stored in each visitor's browser (localStorage). There is no backend yet, so nothing is shared between devices. The owner login is client-side only.
