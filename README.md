<div align="center">

<img src="https://storage.ko-fi.com/cdn/useruploads/post/4577af25-8a01-4cdf-ae95-9093ea50fdc1_neobun.png" width="72" height="72" alt="logo"/>

# MIHON / MANGAYOMI → ANYMEX

**Browser-based manga & anime library migration tool**

[![Live Tool](https://img.shields.io/badge/LIVE%20TOOL-g1nyu.github.io-c8f53a?style=for-the-badge&labelColor=111111)](https://g1nyu.github.io/mihon-to-anymex/)
[![License](https://img.shields.io/badge/LICENSE-MIT-c8f53a?style=for-the-badge&labelColor=111111)](./LICENSE)
[![No Server](https://img.shields.io/badge/SERVER-NONE-c8f53a?style=for-the-badge&labelColor=111111)](#privacy)
[![AniList](https://img.shields.io/badge/POWERED%20BY-ANILIST-02a9ff?style=for-the-badge&labelColor=111111)](https://anilist.co)

</div>

---

## ✦ What It Does

Migrate your entire manga or anime library between apps — complete with **AniList metadata, cover art, ratings, read progress and genres** — all processed locally in your browser.

```
Mihon backup (.json)  ─┐
Mangayomi (.backup)   ─┤──▶  AniList lookup  ──▶  .anymex  ──▶  AnymeX
CSV list              ─┤
Batch titles          ─┘

AnymeX (.anymex)  ──▶  Mihon JSON  ──▶  backup.mihon.tools  ──▶  Mihon
```

---

## ✦ Features

| | Feature | Description |
|:---:|---|---|
| 📥 | **Mihon Import** | Upload a Mihon backup JSON via backup.mihon.tools |
| 📥 | **Mangayomi Import** | Upload a `.backup` file directly — no conversion needed |
| 📄 | **CSV Import** | Plain CSV list of titles with optional status & progress |
| ⚡ | **Batch Add** | Paste titles, fetch AniList, download `.anymex` instantly |
| 🔗 | **Share List** | Compressed URL to share your list with anyone |
| 🖼️ | **Lists Tab** | Shareable cover grid from your `.anymex` backup |
| 🌐 | **EN / JP UI** | Toggle interface between English and Japanese |
| 💾 | **Resume Support** | Interrupted fetches auto-save and resume |
| 🔒 | **100% In-Browser** | Nothing sent to any server except the AniList public API |

---

## ✦ Quickstart

### Mihon → AnymeX

```
1. Mihon → More → Backup & restore → Create backup  (.mihon file)
2. backup.mihon.tools → Upload → Download JSON
3. Upload JSON on the tool → Fetch AniList → Build .anymex
4. AnymeX → Data Management → Restore Data → select file
```

### Mangayomi → AnymeX

```
1. Mangayomi → Settings → Backup & restore → Create backup  (.backup file)
2. Upload .backup directly on the tool → Fetch AniList → Build .anymex
3. AnymeX → Data Management → Restore Data → select file
```

### Batch Add

```
1. Paste titles one per line in the Batch Add card
2. Pick media type + status
3. Drop an existing .anymex to merge into  (optional)
4. ⚡ Fetch & Build → file downloads automatically
```

### Lists Tab

```
1. Click the Lists tab at the top of the page
2. Upload your .anymex file
3. Select a list → enter a display name
4. Share the compressed link on Reddit or Discord
```

---

## ✦ CSV Format

```csv
Solo Leveling,CURRENT,180,Reading
Omniscient Reader,COMPLETED,551,Finished
Vinland Saga,PLANNING,0,Migrated
```

| Column | Required | Default |
|---|:---:|---|
| Title | ✅ | — |
| Status | ❌ | `PLANNING` |
| Chapters Read | ❌ | `0` |
| List Name | ❌ | `Migrated` |

Valid status values: `CURRENT` `PLANNING` `COMPLETED` `DROPPED` `PAUSED` `REPEATING`

---

## ✦ Privacy

All processing happens **entirely in your browser**.
The only external call is to the [AniList public GraphQL API](https://anilist.gitbook.io/anilist-apiv2-docs/) for title lookups.
No data is stored, logged, or transmitted anywhere else.

---

## ✦ File Structure

```
mihon-to-anymex/
├── index.html              ← main app UI (all-in-one)
├── apply-tabs.js           ← injects Convert / Lists tab nav
├── lists.js                ← Lists tab (share & viewer logic)
├── lz-string.min.js        ← URL compression for share links
├── inject-scripts.js       ← sequential script loader
├── mangayomi-to-csv.html   ← standalone Mangayomi helper page
├── anilist_fetch.py        ← legacy Python fetcher
└── build_anymex.py         ← legacy Python builder
```

---

## ✦ License

MIT — free to use, modify and share.

---

<div align="center">

made with ✦ by <a href="https://github.com/G1NYU">G1NYU</a> &nbsp;·&nbsp; <a href="https://anilist.co/user/G1NYU/">AniList</a> &nbsp;·&nbsp; <a href="https://g1nyu.github.io/mihon-to-anymex/">Live Tool</a>

</div>
