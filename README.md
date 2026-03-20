# RandomizerVendor — Minecraft Bedrock Behavior Pack

A custom **Randomizer Vendor** villager for Minecraft Bedrock Edition (1.21+).  
Trade **1 dirt** or **1 stone** to receive a completely random survival item from a pool of 1,258 items.  
Works on **Realms and mobile** — no Script API, no Resource Pack required.

---

## What It Does

- Adds a custom villager called **§d§lRandomizer** (bold magenta name).
- It uses a rare **Swamp Cleric** appearance — no extra artwork needed.
- Two unlimited trades:
  - **1 Dirt → 1 random item**
  - **1 Stone → 1 random item**
- The random pool covers every survival-obtainable item in Bedrock 1.21 (ores, tools, armor, food, mob drops, spawn eggs, music discs, potions, banners, armor trims, and much more — 1,258 entries, all equal weight).
- The villager is **invulnerable**, **immobile**, and **persistent** — it won't wander, despawn, or die.

---

## How to Install

### Option A — Import as `.mcpack` (Easiest)

1. Go to the repo on GitHub and click **Code → Download ZIP**.
2. Unzip the downloaded file.
3. Inside the unzipped folder, find **`RandomizerVendor_BP`**.
4. Zip **just that folder** (right-click → Compress / Send to Zip).
5. **Rename** the resulting `.zip` file to `RandomizerVendor_BP.mcpack`.
6. **Double-click** the `.mcpack` file (Windows/Mac) **or** open it with Minecraft (Android/iOS) to import it.
7. In Minecraft, go to **Settings → Storage** (or the world edit screen) and enable the pack under **Behavior Packs**.
8. Apply it to your world or Realm.

### Option B — Manual Install (Advanced)

1. Download or clone this repo.
2. Copy the `RandomizerVendor_BP` folder into your Minecraft behavior packs directory:
   - **Windows 10/11:** `%APPDATA%\Minecraft\development_behavior_packs\`
   - **Android:** `/sdcard/games/com.mojang/development_behavior_packs/`
   - **iOS:** Files app → `Minecraft → games/com.mojang/development_behavior_packs/`
3. Open Minecraft, edit your world, and activate the pack under **Behavior Packs**.

---

## Spawning the Randomizer Vendor

Once the pack is active in your world or Realm, use either command:

```
/give @p randomizer:randomizer_spawn_egg
```
*(Gives you a spawn egg — place it like any other mob egg.)*

```
/summon randomizer:vendor ~ ~ ~
```
*(Summons the vendor at your current location.)*

---

## Pack Structure

```
RandomizerVendor_BP/
├── manifest.json                   — Pack metadata
├── entities/
│   └── randomizer_vendor.json      — Custom villager entity definition
├── trading/
│   └── randomizer_trades.json      — Two trades (dirt/stone → random item)
└── loot_tables/
    └── randomizer_pool.json        — 1,258 item uniform random pool
```

---

## Requirements

- Minecraft Bedrock Edition **1.21.0** or later
- **Experimental Features** are **not** required
- Works on **Realms**, **mobile (iOS/Android)**, **Windows**, **console**

---

## Notes

- The vendor is **invulnerable** — players cannot kill it.
- The vendor **does not wander** — it stays exactly where you place it.
- Trades **never lock out** — you can trade as many times as you want.
- The random pool excludes technical/creative-only items (barrier, command blocks, structure block, etc.).
