# Viscosity

A browser-based **incremental / idle game** about controlling a hose, spawning driplets, and growing a puddle until the numbers go absurd. Everything runs from a single `index.html` (canvas + UI + logic).

**Live site:** [viscosity.toeffe.uk](https://viscosity.toeffe.uk)

---

## About the game

**Viscosity** is a fluid-themed clicker where you earn **score** and **driplets** (currency) by moving liquid from a suspended hose into a growing **puddle** on the ground. The name nods to how different **liquids** behave: each has its own gravity, spread, bounce, and value multiplier—oil spreads wide, honey is slow and sticky, void-like fluids bend the rules, and late-game recipes push into sci‑fi and cosmic scale.

You **hold the mouse button** and **wiggle** the cursor to build pressure and release driplets faster; upgrades can add **auto-drip**, better flow, combo longevity, and more. When the puddle fills, you advance **puddle levels** and keep climbing. Chaining hits without letting the combo timer expire ramps a **FLOW combo** for extra punch.

Progress is spent in the **Drip Shop**: **Upgrades** (permanent multipliers and quality-of-life), **Pipes** (hoses with different flow and drip value), **Liquids** (unlock wilder fluids as you reach score thresholds), **Achievements**, and a **Board** tab for optional online rankings. **Prestige** resets a run for long-term bonuses; deeper systems include **essence**, milestone bits, and togglable **Overdrive** / **Conservation** modes once unlocked.

The presentation is a monospace HUD with a dark default theme and an optional **light theme** (toggle in the shop header). On **mobile**, the shop opens as a bottom drawer; the custom cursor is disabled so touch play stays comfortable.

---

## How to run locally

No build step is required.

1. Clone or download this repository.
2. Open `index.html` in a modern browser, **or** serve the folder with any static file server (recommended so `file://` quirks are avoided):

   ```bash
   npx serve .
   ```

Progress is saved automatically to **localStorage** in the browser.

---

## Leaderboard (optional)

The **Board** tab can show a Firestore-backed leaderboard using the Firebase JS SDK loaded from `index.html`. Hosting your own copy requires:

- A Firebase project with **Firestore** enabled  
- **Anonymous** sign-in enabled in Firebase Authentication  
- Matching **security rules** (see `firestore.rules` in this repo)  
- Your web app config in the `FIREBASE_CONFIG` object inside `index.html`

If Firebase is not configured or rules block access, the game still plays fully offline; only submission and shared rankings are affected.

---

## Repository layout

| Path | Purpose |
|------|--------|
| `index.html` | Game, styles, and scripts (all-in-one) |
| `firebase.json` | Firebase CLI project metadata (Firestore) |
| `firestore.rules` / `firestore.indexes.json` | Firestore security rules and indexes |
| `CNAME` | Custom domain hint for static hosting |
| `LICENSE` | Apache 2.0 |

---

## License

Licensed under the Apache License 2.0. See [LICENSE](LICENSE).
