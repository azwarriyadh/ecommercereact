
# Next.js Untuk Commerce

## Features

- Performant by default
- SEO Ready
- Internationalization
- Responsive
- UI Components
- Theming
- Standardized Data Hooks
- Integrations - Integrate seamlessly with the most common ecommerce platforms.
- Dark Mode Support

## Integrations

Next.js Commerce terintegrasi langsung dengan BigCommerce, Shopify, Swell, Saleor, Vendure, Spree, dan Commerce.js. Kami berencana untuk mendukung semua backend e-niaga utama.

## Configurasi

### Cara mengganti providers

Open `.env.local` and change the value of `COMMERCE_PROVIDER` to the provider you would like to use, then set the environment variables for that provider (use `.env.template` as the base).

The setup for Shopify would look like this for example:

```
COMMERCE_PROVIDER=shopify
NEXT_PUBLIC_SHOPIFY_STOREFRONT_ACCESS_TOKEN=xxxxxxxxxxxxxxxxxxxxxxxxxxxx
NEXT_PUBLIC_SHOPIFY_STORE_DOMAIN=xxxxxxx.myshopify.com
```

And check that the `tsconfig.json` resolves to the chosen provider:

```
  "@framework": ["framework/shopify"],
  "@framework/*": ["framework/shopify/*"]
```

That's it!

### Features

Setiap provider mendefinisikan fitur yang didukungnya di bawah `framework/{provider}/commerce.config.json`

#### Features Available

Fitur berikut dapat diaktifkan atau dinonaktifkan. Ini berarti bahwa UI akan menghapus semua kode yang terkait dengan fitur tersebut.
Misalnya: Mematikan `cart` akan menonaktifkan kemampuan Cart.

- cart
- search
- wishlist
- customerAuth
- customCheckout

#### Bagaimana Cara Features on dan off

> CATATAN: Penyedia yang dipilih harus mendukung fitur yang Anda aktifkan. (Ini berarti Anda tidak dapat mengaktifkan daftar keinginan jika penyedia tidak mendukung fungsi ini di luar kotak)

- Open `commerce.config.json`
- You'll see a config file like this:
  ```json
  {
    "features": {
      "wishlist": false,
      "customCheckout": true
    }
  }
  ```
- Turn `wishlist` on by setting `wishlist` to `true`.
- Run the app and the wishlist functionality should be back on.

## Troubleshoot

<details>
<summary>I already own a BigCommerce store. What should I do?</summary>
<br>
First thing you do is: <b>set your environment variables</b>
<br>
<br>
.env.local

```sh
BIGCOMMERCE_STOREFRONT_API_URL=<>
BIGCOMMERCE_STOREFRONT_API_TOKEN=<>
BIGCOMMERCE_STORE_API_URL=<>
BIGCOMMERCE_STORE_API_TOKEN=<>
BIGCOMMERCE_STORE_API_CLIENT_ID=<>
BIGCOMMERCE_CHANNEL_ID=<>
```

If your project was started with a "Deploy with Vercel" button, you can use Vercel's CLI to retrieve these credentials.

1. Install Vercel CLI: `npm i -g vercel`
2. Link local instance with Vercel and Github accounts (creates .vercel file): `vercel link`
3. Download your environment variables: `vercel env pull .env.local`

Next, you're free to customize the starter. More updates coming soon. Stay tuned..

</details>

<details>
<summary>BigCommerce shows a Coming Soon page and requests a Preview Code</summary>
<br>
After Email confirmation, Checkout should be manually enabled through BigCommerce platform. Look for "Review & test your store" section through BigCommerce's dashboard.
<br>
<br>
BigCommerce team has been notified and they plan to add more details about this subject.
</details>
