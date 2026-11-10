# Fruit Mart (demo store)

A fictional fresh-produce shop built as a portfolio project. It is one static page
(`index.html`) with all photos embedded, so there is no build step and no server.
Cart, wishlist, orders, sign-in and admin edits are saved in each visitor's own browser.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole site (HTML, CSS, JS, embedded photos) |
| `favicon.svg`, `logo.svg` | Brand assets |
| `robots.txt`, `sitemap.xml` | Search engine files |
| `vercel.json`, `netlify.toml` | Optional hosting settings (use the one for your host) |

## Before you publish
1. Decide your final web address, for example `https://fruitmart-demo.vercel.app`.
2. Replace `YOUR-DOMAIN.com` in `index.html`, `robots.txt` and `sitemap.xml`.
   - Mac/Linux: `sed -i '' 's/YOUR-DOMAIN.com/your-real-domain/g' index.html robots.txt sitemap.xml`
   - Or use find-and-replace in any code editor.
3. Keep the "demo" labels. The site is fictional.

## Deploy on Vercel (free)
**Quickest:** go to vercel.com, sign up, choose **Add New > Project**, and use the drag-and-drop
or import option with this folder. Leave Framework Preset as **Other**, with no build command and
the output directory set to `.`.

**With GitHub:** push this folder to a new repository, then in Vercel choose **Add New > Project**,
import the repository, and click **Deploy**. Every later push redeploys automatically.

**With the CLI:** `npm i -g vercel`, then run `vercel --prod` inside this folder.

## Connect your own domain (Vercel)
Project > **Settings > Domains** > add your domain, then add the DNS records Vercel shows at your
domain registrar (usually an `A` record for the root and a `CNAME` for `www`). HTTPS is automatic.

## Other free hosts
- **Netlify:** drag this folder onto app.netlify.com/drop.
- **GitHub Pages:** push to a repository, then Settings > Pages > deploy from the main branch root.
- **Cloudflare Pages:** connect the repository, no build command, output directory `/`.

## Editing content
- **Prices, names, stock:** use the **Admin demo** page (footer link), or edit the product list
  near the top of the `<script>` in `index.html` (the `const P=` line). Admin edits are saved only
  in the browser that made them.
- **Coupons:** the `COUPONS` object in the script, or the Admin Coupons tab.
- **Photos:** they are embedded as WebP data in `index.html`. To change one, convert the new
  photo to WebP (about 560x420), encode it as base64, and replace the matching entry in the
  `PI` object (hero, category and promo images are the other `const` image entries).
- **Free delivery limit and fee:** search for `499` and `30` in `calc()` and the announcement bar.

## Known limits
- Search engines see one page, because navigation uses `#` links.
- No real payments, orders, accounts or email. All of that is simulated.
- There is no social share image yet. Add a 1200x630 `og-image.jpg` and an
  `og:image` tag if you want link previews.
