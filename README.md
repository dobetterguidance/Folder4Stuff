# Shelf to Supper

**Know what we have. Plan what we'll eat. Buy only what's missing.**

A family kitchen app: freezer/fridge/pantry inventory, a separate spice rack, weekly dinner plans from food you already own, and one shopping list. Works on iPhone, Android and computers. No accounts and no app store.

The app lives in [`app/`](app/). It's plain HTML, so there's nothing to build.

---

## 1. Put it online once (about 10 minutes)

Pick **one** of these. Both re-publish on their own whenever this repo changes, so every phone stays current.

**Option A: Netlify (works with private repos)**
1. Sign in at netlify.com and choose **Add new site → Import an existing project → GitHub**.
2. Pick this repository. Netlify reads `netlify.toml` and publishes the `app/` folder.
3. Copy the `https://….netlify.app` address. You can rename it under *Site settings → Domain*.

**Option B: GitHub Pages**
1. In this repo go to **Settings → Pages → Source: GitHub Actions**.
2. Merge to `main`. The *Publish app* workflow deploys `app/`.
   (Pages on a **private** repo needs a paid GitHub plan. Use Netlify if that's a problem.)

## 2. Install it on each phone

| Phone | Steps |
|---|---|
| **iPhone / iPad** | Open the address in **Safari** → **Share** → **Add to Home Screen** → **Add** |
| **Android** | Open in **Chrome** → **⋮** menu → **Install app** (or *Add to Home screen*) |
| **Computer** | Open in Chrome or Edge → install icon in the address bar (optional) |

The first person to open it sees a **one-screen setup**: household name, where you keep food, and where you shop.

## 3. Get the whole family on the same kitchen

Each phone keeps its own copy on the device. To share:

- **Adding a new phone:** on a phone that's already set up, go to **Settings → Send my updates**. On the new phone, open the app and tap **Open family file** on the welcome screen.
- **Staying in step:** after a big shop or a freezer clean-out, **Send my updates**. Everyone else taps **Merge family updates** and picks that file.
  The merge combines changes. The newest edit of each item wins, deleted items stay deleted, and nothing gets wiped.

> Photos and receipt files stay on the phone that took them. Fully automatic live sync needs household sign-in. That's Phase 2 (see the project guide).

## 4. Keeping it updated

- **App updates:** push a change to `app/` on `main`. Each phone downloads it the next time the app is opened online and shows **"A new version is ready → Refresh."** Your food data is never touched.
- **When you release a change,** bump `CACHE` in `app/sw.js` (for example `shelf-to-supper-v5` → `v6`) and `APP_VERSION` in `app/index.html`.
- **Backups:** the Home screen nudges you if a phone hasn't backed up or shared in two weeks. **Settings → Full backup** saves everything, photos included.

## Family-friendly by design

- **Simple mode** (on by default for new phones, set per phone) shows only Food, Spices, Meals, Shopping and Recipes. Turn it off in Settings for receipts, price trends, space photos and temperatures.
- **Your own stores and spaces.** Add a garage freezer, remove a fridge you don't have, add the farmers market. Nothing is tied to one town.
- Large touch targets, and it works offline once it's been opened.

## Privacy

Household data stays in each phone's browser storage. It isn't uploaded anywhere, and the published site contains no family data. Anyone with the web address can load the empty app, but they can't see your kitchen.

See [`docs/Shelf-to-Supper-Project-Guide.md`](docs/Shelf-to-Supper-Project-Guide.md) for the full brief and roadmap.
