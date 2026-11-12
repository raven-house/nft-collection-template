# Raven House NFT Collection Template

A simple starter kit for creating an NFT collection on Raven House. This repo contains everything you need: example images, an example `metadata.json`, a ready-made `collection.zip`, and a short demo of how to create the zip yourself.

## What's in this repo

| File             | What it is                                           |
| ---------------- | ---------------------------------------------------- |
| `images/`        | Example NFT artwork, named `1.png`, `2.png`, `3.png` |
| `metadata.json`  | The metadata file describing each NFT                |
| `collection.zip` | A complete, valid example ready to upload            |
| `how_to_zip.gif` | A demo of how to zip your files correctly            |

## 1. Prepare your images

- Put all your NFT images inside a folder named **`images`**.
- Supported formats: **PNG, JPG, JPEG** max **5 MB** per image.
- Name them sequentially starting from `1` (`1.png`, `2.png`, `3.png`, ...). No gaps .image `1` becomes NFT #1, image `2` becomes NFT #2, and so on, in the same order as your `nfts` array in `metadata.json`.
- Keep only images in the folder (no other files).

## 2. Fill in `metadata.json`

The file has two parts:

- **`count`**: the total number of NFTs in the collection. This must match the number of images and the number of entries in `nfts`.
- **`nfts`**: an array with one entry per NFT, in order.

Each NFT entry supports:

| Field         | Required | Rules                         |
| ------------- | -------- | ----------------------------- |
| `name`        | Yes      | Up to 100 characters          |
| `description` | No       | Up to 1000 characters         |
| `traits`      | No       | A list of trait / value pairs |

### Trait types

Traits are optional, but if you define trait types when launching your collection, every NFT must include all of them with a matching type. A trait value can be one of three types:

- **Text** (`string`):e.g. `"Protocol Engineer"` (up to 100 characters)
- **Number**: e.g. `42`
- **Boolean**: e.g. `true`

Trait names (`trait_type`) can be up to 31 characters.

```json
"traits": [
  { "trait_type": "Builder Type", "value": "Protocol Engineer" },
  { "trait_type": "Generations", "value": 3 },
  { "trait_type": "Core Contributor", "value": true }
]
```

See [`metadata.json`](./metadata.json) in this repo for a complete working example.

## 3. Create the zip

Select **both** the `images` folder **and** `metadata.json` together, then compress them into a zip. Both must sit at the **top level** of the zip:

```
collection.zip
├── images/
│   ├── 1.png
│   ├── 2.png
│   └── 3.png
└── metadata.json
```

Watch [`how_to_zip.gif`](./how_to_zip.gif) for the exact steps, or just use the ready-made [`collection.zip`](./collection.zip) from this repo as a reference.

## 4. Schedule your mint

When you launch your collection on Raven House, you don't have to open minting immediately. you can **schedule it in advance**. That means you can announce your collection and start building hype today, while the mint automatically opens on the day you chose.

You configure two stages:

- **Whitelist mint**: starts on the date you set, and runs for the duration you set. Whitelisted users get in **early**, at a **different (discounted) price or completely free**compared to the regular public mint.
- **Public mint**: opens later, on its own scheduled date, at the regular mint price.

At least one stage must be scheduled; you can run whitelist-only, public-only, or both.

## 5. Whitelist wallets after launch

When creating the collection you only set the **whitelist schedule and price**, not the actual wallet addresses. After your collection is launched, add the whitelisted wallet addresses **from your profile**. Only you, as the collection creator, can manage your collection's whitelist.

## Need help?

Reach out to us on the Raven House Discord: [https://discord.gg/gCPZhWBYQH](https://discord.gg/gCPZhWBYQH)
