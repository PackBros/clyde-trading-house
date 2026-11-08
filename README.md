# Silver & Form — starter website

A responsive, static HTML/CSS/JavaScript prototype for an independent antique, vintage and sterling silver retailer.

## What's included

- Homepage with brand positioning and featured stock
- Shop page with text search, category filtering and sorting
- Product detail template driven by a sample product catalogue
- Silver Journal landing page and two example educational articles
- About, contact and privacy placeholder pages
- Basic SEO metadata, canonical URL examples and organisation/store structured data
- Responsive styling and local SVG placeholder artwork

## Run locally

Because this is a static site, you can open `index.html` directly in a browser. For the best experience, run a local web server from this folder:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Change the branding

Search the project for `Silver & Form` and replace it with your chosen business name. Update the description, logo treatment, colours and wording in `assets/css/styles.css` and the HTML files.

## Add or edit products

Edit `assets/js/products.js`. Each product object supports:

- `id`, `slug`, `name`, `category`
- `price` (GBP number)
- `weight`, `era`, `condition`, `description`
- `image` (path to a local image)
- `featured` (true/false)
- `date`, `sku`, `purity`

Add product photographs to `assets/images/` and reference them in the `image` field. Use descriptive file names and meaningful alt text. For a real shop, product images should be actual photographs of the exact item being sold.

## Important prototype limitations

This is a front-end example, not a production ecommerce system.

- No basket, checkout, payment processing or order management is connected.
- No database, admin login or secure product-management dashboard exists.
- Product availability is not reserved or updated after a sale.
- Contact details, domain, canonical URLs, legal pages and business identity are placeholders.
- The product images are simple SVG illustrations, not photos of real inventory.
- Google Fonts are loaded from Google; remove the import if you prefer fully self-hosted assets.

Before accepting orders, connect a secure ecommerce platform or backend (for example Shopify or another established commerce provider), configure payment and delivery, add real product photography, write accurate terms/returns/privacy policies, and test the full customer journey.

## SEO launch checklist

1. Replace every `https://example.com` canonical URL with the real domain.
2. Write unique page titles and meta descriptions for each real page/product.
3. Add descriptive, accurate product copy; do not invent hallmark dates, makers or weights.
4. Generate a full sitemap.xml and robots.txt for the production domain.
5. Add product structured data from actual product data, including price, currency, availability and condition.
6. Set up Google Search Console and submit the sitemap.
7. Create a Google Business Profile only if eligible under Google's guidelines; use accurate business details.
8. Add analytics with an appropriate privacy/cookie setup.
9. Make category pages useful and avoid mass-producing near-identical SEO pages.
10. Keep sold product pages useful: mark sold, remove purchase prompts, or redirect only where appropriate.

## Suggested production architecture

For a small launch, Shopify with a custom theme is the fastest route to reliable checkout, stock and order handling. A custom frontend with a managed commerce backend gives more control but costs more to build and maintain. Keep the customer-facing site simple; make product entry, SEO fields and stock management easy for the owner.


## Version 2 additions

- Friendlier, lighter storefront styling with simpler navigation and rounded calls to action.
- Homepage newsletter sign-up section. It is a front-end demo only and does not collect or send email addresses yet.
- Consent-first demo event tracking for product views and on-site searches.
- `analytics.html` owner preview showing top product views and search terms from the current browser only.
- `assets/js/insights.js` and `assets/js/analytics-dashboard.js` contain the prototype tracking/reporting logic.

### Important analytics and marketing notes

The demo stores events locally in the visitor's browser after they choose "Allow analytics". It does not show what all customers are viewing and it does not send data to you. For real multi-visitor reporting, connect a privacy-configured analytics provider or build a server-side event endpoint. Put the reporting dashboard behind a secure owner login. Do not use fingerprinting or collect unnecessary personal data.

For real email marketing, connect the form to a provider such as Mailchimp, Klaviyo or Brevo, use confirmed/recorded opt-in where appropriate, provide an unsubscribe link in every marketing email, and update the privacy notice. The prototype deliberately does not store or transmit email addresses.

Before launch, configure a consent management solution appropriate to UK privacy/ePrivacy requirements. The prototype consent banner is illustrative, not legal compliance certification.


## Version 3 design changes

- Removed the three-column trust/benefits band from the homepage.
- Added a first-visit welcome popup with sample categories and product imagery.
- Popup has Continue, close button, backdrop click and Escape key dismissal.
- The dismissal is remembered on the same device using localStorage.
- The popup is injected on pages that load `assets/js/insights.js`; it is a shop introduction, not a newsletter or advertising popup.


## Version 4 changes

- Removed the pastel/green styling in favour of a clean white, black and neutral-grey palette.
- Welcome popup's primary Continue button now sends visitors directly to `shop.html`, the product browser.
- Shop browser has quick category chips as well as a category dropdown, search and sort.
- Search checks product name, category, era, description, SKU, purity, condition and weight; multi-word searches require all terms to match.
- Category chips and dropdown stay synchronised.

The demo catalogue is still sample data. The product browser works against `assets/js/products.js`. Production search needs a real product database and server-side indexing once the catalogue grows.


## Version 5 changes

- Reworked visual identity into an editorial/gallery-led white storefront. Dark tones are used for typography and fine outlines, not large filled blocks.
- Product photography has more visual priority, with generous white space and restrained product information.
- Added persistent heart/favourites controls to featured products, collection cards and product detail pages. Saved products are available on `saved.html`; favourites persist in the same browser using localStorage.
- Replaced product enquiry actions with `Buy now`, linking to `checkout.html?item=...`.
- Added a checkout review step. Payment processing is not integrated yet, so do not treat the prototype as a live store.
- Added a saved-items counter in the header.

Important: saved items are stored on the visitor's device only. A real cross-device customer account and payment checkout require backend development and secure payment-provider integration.


## Version 6: customer walkthrough demo

- Added nine locally stored generated product photographs, cropped from an original studio contact sheet. These are illustrative AI-generated images, not photographs of actual stock.
- Expanded the sample catalogue to nine products with illustrative GBP prices and descriptions.
- Added a simulated checkout flow with delivery detail fields and a demo order confirmation.
- The checkout is deliberately non-payment: it does not transmit or store personal details and no real order is created.
- Use the popup on a first visit, continue to the shop, search/filter, open a product, save it, and try Buy Now.
- To replay the welcome popup, clear local site storage for this file/site or remove `silverform_welcome_seen` from browser local storage.
