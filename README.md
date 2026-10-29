# Adventist Lifestyle Bookstore

A responsive React + Vite + TypeScript storefront for Adventist Lifestyle Bookstore, part of Adventist Centre Lifestyle.

## Run locally

```bash
npm install
npm run dev
```

Create a production build with `npm run build` and preview it with `npm run preview`.

## Included

- Responsive storefront with age-based browsing, product search, sorting, filters, product details, special offers, and an empty-results state.
- Cart with quantity controls, remove actions, subtotal calculations, and `localStorage` persistence.
- WhatsApp order-enquiry handoff to **+27 76 547 1961** using a URL-encoded message. Opening WhatsApp does not confirm an order; the customer must send the message and the store must confirm availability and final costs.
- Local editable product catalogue in `src/data/products.ts`; each entry has a unique ID and media fields.
- Clearly labelled book-cover and preview placeholders. No real cover images or fabricated readable pages are included.
- Reduced-motion support and keyboard-accessible controls/dialogs.

## Replace placeholders with supplied media

Put supplied assets under `public/media/`, then update each product's `media` object in `src/data/products.ts`:

```ts
media: {
  cover: '/media/your-actual-cover.webp',
  previewImages: ['/media/page-01.webp', '/media/page-02.webp'],
  previewVideo: '/media/your-preview.mp4', // optional
  alt: 'Accurate description of the supplied cover'
}
```

Product card covers will use the actual cover path when populated. The product-detail modal currently explains that page previews will be added when supplied; connect `previewImages` / `previewVideo` there when the files are available. Replace the CSS sunrise artwork in the hero with the supplied hero image if desired, while preserving the text contrast overlay. Replace the stylized David/Samson placeholder scene with supplied artwork when available.

## Content owner checks before publishing

- Add the full 2 Corinthians 4:6 verse and identify the translation once supplied. The current hero only shows the reference and a clear placeholder.
- Verify the supplied catalogue title **“KJV Amplified Bible”** before publishing.
- Two NLT Inspire Bible entries are intentionally separate (`nlt-inspire-699` and `nlt-inspire-650`) because their prices differ.
- Prices and previous prices are only the values supplied. No shipping charge, stock quantity, review, staff endorsement, or order confirmation is invented.
- The WhatsApp catalogue is linked as an external catalogue; live synchronisation is not claimed.

## Styling / stack

- React, Vite, TypeScript
- Tailwind CSS configured (with bespoke CSS for the storefront design)
- Motion for React (`motion/react`)
- lucide-react icons
- Libre Baskerville + Inter fonts

The current design uses a CSS-generated sunrise and labelled cover placeholders so the storefront works before media upload. `shadcn/ui` is not imported; the UI components are purpose-built to keep the starter project self-contained.
