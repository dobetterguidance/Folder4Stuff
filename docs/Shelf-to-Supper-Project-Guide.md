# Shelf to Supper — App Project Guide

**Version:** 5 (October 25, 2026)
**Purpose:** A low-effort family kitchen inventory, meal-planning and grocery-shopping app that any household can set up.
**Core principle:** Know what we have. Plan what we'll eat. Buy only what's missing.

> **What changed in v5:** The app is no longer hard-coded to one town or one kitchen layout. It adds a one-screen family setup, Simple mode, per-family stores and storage spaces, sharing between phones without accounts, and automatic app updates. Install and sharing steps are in the [README](../README.md).

---

## 1. App Brief

Build a mobile-first app called **Shelf to Supper** for a household of any size, anywhere. The original family is in the Alexandria, Minnesota area, and their stores ship as a preset. Keep it extremely simple: take a photo or scan a receipt, review what was recognized, and tap once to update inventory. Generate practical weekly dinners from food on hand and a short list of missing ingredients. Design for the whole family on their own phones, including kids and grandparents.

### A. Storage and inventory
- **Any number of storage spaces**, each with a custom name and type (freezer, refrigerator, pantry, plus a dedicated spice rack). The default suggestions are Freezer 1–3, Refrigerator 1–2, Pantry, Beverage refrigerator and Spice rack. Families pick what they have during setup and can add or remove spaces later.
- Per space: photos, manufacturer/model, capacity, interior dimensions, shelves/drawers/baskets/zones. Shelf photos are verified by a person before items are added. Never present a photo as a reliable measurement of hidden contents or capacity.
- Per item: name, category, amount, unit, package size, brand, space/zone, purchase, best-by and open dates, and notes. Items can be added, transferred, used up, split and discarded. Show warnings for low stock and aging food, with "expiring soon" and "use first" filters.

### B. Spice rack
A spice inventory separate from the pantry: name, brand, container, quantity, unit, rack position, open and best-by dates, and minimum amount. Includes refill suggestions that feed the grocery list. Recognizes common Asian, Mexican, American and Italian seasonings.

### C. Weekly meal planning and recipes
- 3–7 dinners a week, chosen from inventory, serving counts, use-soon food and household preferences. Dishes missing only a few ingredients come first.
- Asian, Mexican, American and Italian cuisines, with gluten-free filters.
- Families can save favorites, change servings, swap meals and add their own recipes.
- A freezer-pull/thaw list. Confirming a transfer updates inventory.

### D. Grocery list and stores
- One editable list that combines meal-plan shortages, spice refills, low-stock essentials and manual items. It groups duplicates and normalizes quantities. Items can be checked off, assigned to stores and organized by trip.
- **Each household manages its own store list**, with three types: local, bulk/warehouse (Costco, Sam's Club, BJ's) and online (Walmart, Amazon, Amazon Fresh, Instacart, Weee!). Common national chains are one tap in setup, and any local store can be added by name. A store without a link opens a map search near the household's town or ZIP.
- Separate views for weekly shopping, bulk stock-up trips and online orders.
- Never claim availability, delivery eligibility or prices that haven't been verified.

### E. Receipts and invoices
Accept phone photos, scans or PDF invoices. Keep the original document. Track retailer, date, line items, quantity, size, unit, unit price, discounts, tax and total, and let the family review entries before adding them to inventory. *Future:* OCR/AI extraction with human confirmation. Don't claim automatic extraction until it works.

### F. Spending trends and buying power
Built from saved purchase records only:
- Spending by week, month, category and store.
- Per-item price history.
- True unit prices.
- Whether a bulk package is worth it (usable amount, waste risk, optional trip cost).
- Frequent purchases and savings opportunities.

Label missing data clearly. Never invent deals or prices.

### G. Temperatures
A manual log for every refrigerator and freezer, with out-of-range warnings, kept separate from inventory changes. Sensors, push alerts and trend charts come later.

### H. Family use and data safety
- **Now (v5):** each phone stores its own copy. Families share by sending an updates file and merging it on the other phones. Records carry change times and deletion markers, so merges combine edits without overwriting.
- **Production:** household accounts, live sync across phones, private photo/PDF storage, backup/restore, offline use and access controls.
- Shopping and receipt data are private household information. Label prototype features clearly.

### I. UX expectations
- Large touch targets and simple navigation.
- **Simple mode**, set per phone, hides receipts, trends, space photos and temperatures.
- Very few steps to add food or plan dinner.
- At-a-glance dashboard: in stock, expiring, this week's dinners, items to thaw, items to buy, temperature warnings.
- A **one-screen first-run setup**: household, spaces, stores.
- Install on iPhone, Android or a computer with no folders or code to manage. Updates arrive on their own.

### J. Success criteria
1. A family member can find which freezer holds an item in seconds.
2. The weekly plan uses existing inventory before suggesting purchases.
3. A single shopping list includes recipe shortages and manual additions.
4. Receipts feed spending charts and price history.
5. Spice quantities and low-stock reminders are separate from pantry items.
6. A new household anywhere can set up in under two minutes without editing code.
7. Two phones end up with the same inventory after exchanging updates (v5), or automatically (Phase 2).

---

## 2. What's in Version 5

**Everything from v4:** storage spaces, spice rack, meal planning, editable shopping lists, store suggestions, receipt recording, appliance photos and profiles, spending and price comparisons, and the temperature log.

**New in v5:**

| Area | What it does |
|---|---|
| Universal setup | One-screen welcome (household, spaces, stores). Add, rename or remove spaces and stores in Settings. No hard-coded town. |
| Simple mode | A per-phone switch that hides advanced tools. On by default for new phones. |
| Family sharing | **Send my updates** and **Merge family updates** (Messages, AirDrop, email, shared folder). **Open family file** when joining from a new phone. |
| Auto-updates | Phones fetch new versions in the background and show a **Refresh** notice. A **Check for update** button is in Settings. |
| Safety nets | Home-screen reminder to back up or share after two weeks. Spaces that still hold food can't be deleted. Stores used on receipts are kept for price history. |
| iPhone polish | Proper home-screen icon, standalone app mode, larger touch targets. |

**Existing v4 households upgrade in place.** Inventory, recipes, receipts, photos, the eight spaces and the Alexandria store list are all kept.

**Still not included:** reliable AI shelf or receipt recognition, live prices, online checkout, hands-free cloud sync, or wireless temperature sensors.

---

## 3. Getting Started

See the [README](../README.md) for publishing (Netlify or GitHub Pages), installing on iPhone and Android, and adding family phones.

> **Privacy note:** The published site holds only the empty app. Household data stays in each phone's browser. Don't commit household data, receipts or photos to this repository.

---

## 4. Development Order

**Phase 1 — Easy for the family:** ✅ v5
- ✅ Stable hosting with auto-deploy
- ✅ Onboarding
- ✅ Simple mode
- ✅ Backup reminders
- ✅ Sharing between phones
- ☐ Test on every household phone

**Phase 2 — Live shared data:**
- Sign-in, a shared household database and private photo/receipt storage.
- The v5 change tracking (`_u` change times and deletion markers) is designed to carry over to cloud sync.
- Suggested stack: Supabase or Firebase. The free tiers cover one household.

**Phase 3 — Less typing:** barcode scanning, AI-assisted shelf and spice recognition, and OCR receipt import, each with a quick approval screen.

**Phase 4 — Better buying decisions:** normalized package comparisons, trusted retailer price integrations where offered, and bulk-trip recommendations.

**Phase 5 — Automation:** wireless temperature sensors, alerts and use-before-expiry suggestions.

---

## 5. File and Version Notes
- **App:** `app/` (`index.html`, `manifest.webmanifest`, `sw.js`, icons).
- **Releasing a change:** bump `CACHE` in `app/sw.js` and `APP_VERSION` in `app/index.html`.
- **Data compatibility:** browser storage key `shelf-to-supper-v1` is unchanged. Per-phone preferences live in `shelf-to-supper-device` and are never shared.
- Save a **Full backup** before changing the website address. A new address starts with empty storage. Restore the backup or open a family file there.
