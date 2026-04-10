# warera-api-docs Setup Plan

> **For agentic workers:** Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Set up a public GitHub Pages site (`warera-api-docs`) hosting community-made WarEra tRPC API endpoint documentation using Docsify.

**Architecture:** Static site powered by Docsify — zero build step, reads `.md` files directly. Specs are organized by `namespace.method` folders, each with a `spec.md` (human-readable) and `spec.json` (machine-readable). GitHub Pages serves the site from the repo root on the `main` branch.

**Tech Stack:** Docsify (CDN, no install), GitHub Pages, Markdown, JSON

**Starting point:** You are in the `warera-api-docs` folder. The repo has already been created on GitHub under an org. The specs content will be copied from another project — steps below tell you exactly what to create.

---

## File Structure

```
warera-api-docs/
├── index.html              # Docsify entry point + config
├── _sidebar.md             # Navigation tree
├── .nojekyll               # Prevents GitHub Pages from ignoring _files
├── README.md               # Landing page shown at /
└── specs/
    ├── article.getArticleById/
    │   ├── spec.md
    │   └── spec.json
    ├── article.getArticleLiteById/
    │   ├── spec.md
    │   └── spec.json
    ├── article.getArticlesPaginated/
    │   ├── spec.md
    │   └── spec.json
    ├── battle.getById/
    │   ├── spec.md
    │   └── spec.json
    ├── battle.getBattles/
    │   ├── spec.md
    │   └── spec.json
    ├── battle.getLiveBattleData/
    │   ├── spec.md
    │   └── spec.json
    ├── battleRanking.getRanking/
    │   ├── spec.md
    │   └── spec.json
    ├── country.getAllCountries/
    │   ├── spec.md
    │   └── spec.json
    ├── country.getCountryById/
    │   ├── spec.md
    │   └── spec.json
    ├── event.getEventsPaginated/
    │   ├── spec.md
    │   └── spec.json
    ├── itemTrading.getPrices/
    │   ├── spec.md
    │   └── spec.json
    ├── mu.getById/
    │   ├── spec.md
    │   └── spec.json
    ├── party.getById/
    │   ├── spec.md
    │   └── spec.json
    ├── ranking.getRanking/
    │   ├── spec.md
    │   └── spec.json
    ├── referral.getUserReferrals/
    │   ├── spec.md
    │   └── spec.json
    ├── referral.getUserReferralsPaginated/
    │   ├── spec.md
    │   └── spec.json
    ├── region.getById/
    │   ├── spec.md
    │   └── spec.json
    ├── region.getRegionsObject/
    │   ├── spec.md
    │   └── spec.json
    ├── sanction.getPaginated/
    │   ├── spec.md
    │   └── spec.json
    ├── search.searchAnything/
    │   ├── spec.md
    │   └── spec.json
    ├── tradingOrder.getTopOrders/
    │   ├── spec.md
    │   └── spec.json
    ├── user.getUserLite/
    │   ├── spec.md
    │   └── spec.json
    └── user.getUsersByCountry/
        ├── spec.md
        └── spec.json
```

---

## Task 1: Copy specs from source project

**Files:**
- Create: `specs/` — copied from the Kiwami project

- [ ] **Step 1: Copy the specs folder**

  The source is the `specs/` folder from the Kiwami project (wherever that lives on your machine). Copy the entire folder into the root of `warera-api-docs/`. After this step, `warera-api-docs/specs/` should contain 23 subdirectories, each with `spec.md` and `spec.json`.

  Verify:
  ```bash
  ls specs/ | wc -l
  # expected: 23
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add specs/
  git commit -m "feat: add initial endpoint specs"
  ```

---

## Task 2: Create Docsify entry point

**Files:**
- Create: `index.html`
- Create: `.nojekyll`

- [ ] **Step 1: Create `.nojekyll`**

  This empty file tells GitHub Pages not to use Jekyll, which would otherwise skip files starting with `_` (like `_sidebar.md`).

  Create an empty file named `.nojekyll` in the repo root. No content needed.

- [ ] **Step 2: Create `index.html`**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>WarEra API Docs (Community)</title>
    <meta name="description" content="Community-made endpoint documentation for the WarEra tRPC API. Not affiliated with WarEra developers." />
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css" />
    <style>
      .disclaimer-banner {
        background: #fff3cd;
        border: 1px solid #ffc107;
        border-radius: 4px;
        padding: 10px 16px;
        margin: 0 0 1.5em 0;
        font-size: 0.9em;
        color: #856404;
      }
    </style>
  </head>
  <body>
    <div id="app"></div>
    <script>
      window.$docsify = {
        name: 'WarEra API Docs',
        repo: '',
        loadSidebar: true,
        subMaxLevel: 2,
        search: {
          placeholder: 'Search endpoints...',
          noData: 'No results found.',
          depth: 3
        },
        plugins: [
          function (hook) {
            hook.beforeEach(function (content) {
              return content;
            });
          }
        ]
      };
    </script>
    <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/docsify.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.min.js"></script>
  </body>
  </html>
  ```

- [ ] **Step 3: Commit**

  ```bash
  git add index.html .nojekyll
  git commit -m "feat: add Docsify entry point and nojekyll"
  ```

---

## Task 3: Create landing page (README.md)

**Files:**
- Create: `README.md`

- [ ] **Step 1: Create `README.md`**

  This file is served as the home page by Docsify (maps to `/`).

  ```markdown
  # WarEra API — Community Documentation

  > **Disclaimer:** This documentation is community-made and is **not affiliated with, endorsed by, or maintained by the WarEra development team**. It was created by exploring the API endpoints and observing response structures. It may be incomplete or out of date. Use at your own discretion.

  ## What is this?

  [WarEra](https://warera.io) is a browser-based strategy game. Its backend exposes a [tRPC](https://trpc.io) API at `https://api2.warera.io/trpc/`.

  The official API docs at [api2.warera.io/docs/](https://api2.warera.io/docs/) list available endpoints but do not document response structures. This site fills that gap.

  ## How to use

  Browse endpoints using the sidebar. Each endpoint page documents:

  - **Auth** — whether authentication is required or optional
  - **Input** — parameters the endpoint accepts
  - **Output** — full response structure with field types
  - **Notes** — observed quirks and aliases
  - **Example request** — a ready-to-use URL

  A machine-readable `spec.json` is available alongside each `spec.md` for programmatic use.

  ## Making requests

  WarEra uses tRPC, which maps to HTTP GET requests:

  ```
  GET https://api2.warera.io/trpc/<namespace>.<method>
  GET https://api2.warera.io/trpc/<namespace>.<method>?input=<JSON>
  ```

  For authenticated endpoints, include your session token as a Bearer token in the `Authorization` header.

  ## Contributing

  Found an undocumented endpoint or a field that's wrong? PRs are welcome. Follow the existing `spec.md` and `spec.json` format in the `specs/` folder.
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add README.md
  git commit -m "docs: add landing page with disclaimer"
  ```

---

## Task 4: Create sidebar navigation

**Files:**
- Create: `_sidebar.md`

- [ ] **Step 1: Create `_sidebar.md`**

  ```markdown
  - [Home](/)

  - **Article**
    - [article.getArticleById](specs/article.getArticleById/spec.md)
    - [article.getArticleLiteById](specs/article.getArticleLiteById/spec.md)
    - [article.getArticlesPaginated](specs/article.getArticlesPaginated/spec.md)

  - **Battle**
    - [battle.getById](specs/battle.getById/spec.md)
    - [battle.getBattles](specs/battle.getBattles/spec.md)
    - [battle.getLiveBattleData](specs/battle.getLiveBattleData/spec.md)
    - [battleRanking.getRanking](specs/battleRanking.getRanking/spec.md)

  - **Country**
    - [country.getAllCountries](specs/country.getAllCountries/spec.md)
    - [country.getCountryById](specs/country.getCountryById/spec.md)

  - **Event**
    - [event.getEventsPaginated](specs/event.getEventsPaginated/spec.md)

  - **Item Trading**
    - [itemTrading.getPrices](specs/itemTrading.getPrices/spec.md)
    - [tradingOrder.getTopOrders](specs/tradingOrder.getTopOrders/spec.md)

  - **Military Unit**
    - [mu.getById](specs/mu.getById/spec.md)

  - **Party**
    - [party.getById](specs/party.getById/spec.md)

  - **Ranking**
    - [ranking.getRanking](specs/ranking.getRanking/spec.md)

  - **Referral**
    - [referral.getUserReferrals](specs/referral.getUserReferrals/spec.md)
    - [referral.getUserReferralsPaginated](specs/referral.getUserReferralsPaginated/spec.md)

  - **Region**
    - [region.getById](specs/region.getById/spec.md)
    - [region.getRegionsObject](specs/region.getRegionsObject/spec.md)

  - **Sanction**
    - [sanction.getPaginated](specs/sanction.getPaginated/spec.md)

  - **Search**
    - [search.searchAnything](specs/search.searchAnything/spec.md)

  - **User**
    - [user.getUserLite](specs/user.getUserLite/spec.md)
    - [user.getUsersByCountry](specs/user.getUsersByCountry/spec.md)
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add _sidebar.md
  git commit -m "docs: add sidebar navigation for all 23 endpoints"
  ```

---

## Task 5: Enable GitHub Pages

- [ ] **Step 1: Push all commits to GitHub**

  ```bash
  git push origin main
  ```

- [ ] **Step 2: Enable GitHub Pages in repo settings**

  1. Go to the repo on GitHub
  2. Settings → Pages
  3. Source: **Deploy from a branch**
  4. Branch: `main` / `/ (root)`
  5. Save

- [ ] **Step 3: Verify the site is live**

  GitHub will show the Pages URL after saving — typically `https://<org-name>.github.io/warera-api-docs/`. Wait ~60 seconds for the first deploy, then open the URL.

  Check:
  - Home page loads with disclaimer
  - Sidebar shows all namespace groups
  - Clicking an endpoint renders the spec
  - Search box works (try typing `sanction`)

---

## Done

The site is live. Future additions: add a new `specs/<namespace.method>/` folder with `spec.md` + `spec.json`, add a line to `_sidebar.md`, push — the site updates automatically.
