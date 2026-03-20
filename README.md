# RandomizerVendor — Minecraft Bedrock Behavior Pack

A custom **Randomizer Vendor** villager for Minecraft Bedrock Edition (1.21+).  
Trade **1 dirt** or **1 cobblestone** to receive a completely random survival item from a pool of 1,258 items.  
Works on **Realms and mobile** — no Script API required.  
Requires both the **Behavior Pack** and the **Resource Pack** (included in this repo).

---

## What It Does

- Adds a custom villager called **§d§lRandomizer** (bold magenta name).
- It uses a **Swamp Cleric** appearance via vanilla Bedrock assets — the Resource Pack (included) points to the built-in villager textures, so no custom artwork is needed.
- Two unlimited trades:
  - **1 Dirt → 1 random item**
  - **1 Cobblestone → 1 random item**
- The random pool covers every survival-obtainable item in Bedrock 1.21 (ores, tools, armor, food, mob drops, spawn eggs, music discs, potions, banners, armor trims, and much more — 1,258 entries, all equal weight).
- The villager is **invulnerable**, **immobile**, and **persistent** — it won't wander, despawn, or die.

---

## How to Install

> **Both packs are required** — the Behavior Pack (BP) provides the logic and trades; the Resource Pack (RP) provides the model and textures.  
> Without the RP the vendor will be invisible.

### Option A — Import as `.mcpack` (Easiest)

1. Go to the repo on GitHub and click **Code → Download ZIP**.
2. Unzip the downloaded file.
3. **Import the Behavior Pack:**
   - Inside the unzipped folder, find **`RandomizerVendor_BP`**.
   - Zip **just that folder** and rename it to `RandomizerVendor_BP.mcpack`.
   - Double-click (Windows/Mac) or open with Minecraft (Android/iOS) to import.
4. **Import the Resource Pack:**
   - Do the same for **`RandomizerVendor_RP`** → zip it → rename to `RandomizerVendor_RP.mcpack` → import.
5. In Minecraft, edit your world and enable **both packs**: the BP under **Behavior Packs** and the RP under **Resource Packs**.
6. Apply to your world or Realm.

### Option B — Manual Install (Advanced)

1. Download or clone this repo.
2. Copy `RandomizerVendor_BP` into your behavior packs directory:
   - **Windows 10/11:** `%APPDATA%\Minecraft\development_behavior_packs\`
   - **Android:** `/sdcard/games/com.mojang/development_behavior_packs/`
   - **iOS:** Files app → `Minecraft → games/com.mojang/development_behavior_packs/`
3. Copy `RandomizerVendor_RP` into your resource packs directory:
   - **Windows 10/11:** `%APPDATA%\Minecraft\development_resource_packs\`
   - **Android:** `/sdcard/games/com.mojang/development_resource_packs/`
   - **iOS:** Files app → `Minecraft → games/com.mojang/development_resource_packs/`
4. Open Minecraft, edit your world, and activate the BP under **Behavior Packs** and the RP under **Resource Packs**.

---

## Spawning the Randomizer Vendor

Once the pack is active in your world or Realm, use either command:

```
/give @p randomizer:vendor_spawn_egg
```
*(Gives you a spawn egg — place it like any other mob egg.)*

```
/summon randomizer:vendor ~ ~ ~
```
*(Summons the vendor at your current location.)*

To give the vendor its purple name after spawning, run:
```
/name @e[type=randomizer:vendor,r=5] "§d§lRandomizer"
```

---

## Pack Structure

```
RandomizerVendor_BP/             ← Behavior Pack (logic, trades)
├── manifest.json
├── entities/
│   └── randomizer_vendor.json   — Entity definition (server-side)
├── trading/
│   └── randomizer_trades.json   — Two trades (dirt/cobblestone → random item)
└── loot_tables/
    └── randomizer_pool.json     — 1,258-item uniform random pool

RandomizerVendor_RP/             ← Resource Pack (model, textures) — REQUIRED
├── manifest.json
└── entity/
    └── randomizer_vendor.entity.json  — Client entity (geometry + texture + spawn egg)
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
