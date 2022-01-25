
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

Buka `.env.local` dan ganti value of `COMMERCE_PROVIDER` ke provider yang akan dipakai, lalu set the environment variables untuk providernya (gunakan `.env.template` sebagai the base).

Setup untuk Shopify terlihat seperti contoh dibawah:

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

Jalankan

### Features

Setiap provider mendefinisikan fitur yang didukungnya di bawah `framework/{provider}/commerce.config.json`
Fitur berikut dapat diaktifkan atau dinonaktifkan. Ini berarti bahwa UI akan menghapus semua kode yang terkait dengan fitur tersebut.
Misalnya: Mematikan `cart` akan menonaktifkan kemampuan Cart.

- cart
- search
- wishlist
- customerAuth
- customCheckout

#### Bagaimana Cara Features on dan off

> CATATAN: Penyedia yang dipilih harus mendukung fitur yang Anda aktifkan. (Ini berarti Anda tidak dapat mengaktifkan daftar keinginan jika penyedia tidak mendukung fungsi ini di luar kotak)

- Buka `commerce.config.json`
- Akan terlihat seperti ini:
  ```json
  {
    "features": {
      "wishlist": false,
      "customCheckout": true
    }
  }
  ```
- Nyalakan `wishlist` dengan mensetting `wishlist` ke `true`.
- Jalankan aplikasi dan fungsi wishlist functionality kembali menyala.

## Troubleshoot

<details>
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

</details>

