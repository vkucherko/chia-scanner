<h1 align="center">Chia</h1>

<p align="center">
  <img src="docs/brand/app-icon.png" width="116" alt="Chia app icon" />
</p>

<p align="center">The honest answer to "is this food actually healthy?", in under a second, even offline.</p>

<p align="center">
  <img src="docs/brand/hero-slav.svg" width="100%" alt="Terminal: slav@quality-engineer runs an agentic QA pipeline, story to design to generate to run to heal to green. AI Quality Engineer, 9+ years." />
</p>

<p align="center">
  <img src="docs/brand/hero.svg" width="100%" alt="Chia: scan a food barcode, get an instant pass/fail verdict. The viewfinder frames a strawberry Greek yogurt on a fridge shelf; the scan resolves to a wilted leaf and 'Better options out there' because it contains Red 40; alongside, a pipeline log runs scan → cache → edge → merge → eval → FAIL." />
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/kucherko/"><img src="docs/brand/badge-linkedin.svg" height="26" alt="LinkedIn: kucherko" /></a>
  <a href="mailto:vkucherko7@gmail.com"><img src="docs/brand/badge-email.svg" height="26" alt="Email: vkucherko7" /></a>
</p>

Chia is an iOS-first barcode scanner that gives you an instant pass / fail verdict on packaged foods, based on their actual ingredients and additives. Not a vague score, not a paywall, not a five-screen nutrition essay. Point the camera at a barcode; get a warm, honest answer with the reasons behind it.

<br />

<p align="center">
  <img src="https://img.shields.io/badge/platform-iOS-000000?style=flat-square&logo=apple&logoColor=white" alt="Platform iOS" />
  <img src="https://img.shields.io/badge/React_Native-0.85.3-61DAFB?style=flat-square&logo=react&logoColor=white" alt="React Native 0.85.3" />
  <img src="https://img.shields.io/badge/Expo_SDK-56-000020?style=flat-square&logo=expo&logoColor=white" alt="Expo SDK 56" />
  <img src="https://img.shields.io/badge/React-19.2.3-149ECA?style=flat-square&logo=react&logoColor=white" alt="React 19.2.3" />
  <img src="https://img.shields.io/badge/TypeScript-6.0.3_strict-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript 6.0.3 strict" />
  <img src="https://img.shields.io/badge/Cloudflare_Workers-Hono_4.6-F38020?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare Workers" />
  <img src="https://img.shields.io/badge/Supabase-Postgres_+_RLS-3ECF8E?style=flat-square&logo=supabase&logoColor=white" alt="Supabase" />
  <img src="https://img.shields.io/badge/tests-30_files_·_400+_cases-6E9B6E?style=flat-square" alt="Tests" />
</p>

<br />

<p align="center">
  <a href="#does"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-does.dark.svg" /><img src="docs/brand/ui/navbtn-does.svg" height="34" alt="What it does" /></picture></a>
  <a href="#arch"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-arch.dark.svg" /><img src="docs/brand/ui/navbtn-arch.svg" height="34" alt="Architecture" /></picture></a>
  <a href="#eng"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-eng.dark.svg" /><img src="docs/brand/ui/navbtn-eng.svg" height="34" alt="Engineering" /></picture></a>
  <a href="#stack"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-stack.dark.svg" /><img src="docs/brand/ui/navbtn-stack.svg" height="34" alt="Tech stack" /></picture></a>
  <a href="#roadmap"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-roadmap.dark.svg" /><img src="docs/brand/ui/navbtn-roadmap.svg" height="34" alt="Roadmap" /></picture></a>
  <a href="#more"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/navbtn-more.dark.svg" /><img src="docs/brand/ui/navbtn-more.svg" height="34" alt="Contact" /></picture></a>
</p>

<p><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/source.dark.svg" /><img src="docs/brand/title/source.svg" height="32" align="absmiddle" alt="A note on the source" /></picture></p>

This repository is a public showcase: architecture, design decisions, and engineering write-ups. The application source is private while Chia is in active, pre-launch development.

If you're a recruiter or engineer and want to go deeper, I'm happy to give a live walkthrough or set up a TestFlight build. See the [footer](#more).

<a id="does"></a>

<p><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/does.dark.svg" /><img src="docs/brand/title/does.svg" height="32" align="absmiddle" alt="What it does" /></picture></p>

Chia is built around one fast, honest interaction.

Scan. An embedded 240px viewfinder reads the barcode. (It's not a full-screen camera; the camera session stops shortly after you leave the tab, so it isn't quietly draining your battery.)

Verdict. The product is matched against a curated rule set on your device and you get a single verdict, delivered through four redundant signals at once:

| Signal | Pass | Fail |
| --- | --- | --- |
| Color | sage | terracotta |
| Icon | animated leaf, upright | animated leaf, wilted, stroke-drawn on entry |
| Text | one of 10 warm phrases ("Great pick!") | one of 10 calm phrases ("Better options out there") |
| Haptic | Light impact on commit | Light impact on commit |

The phrasing is drawn deterministically per scan, so the same scan never flickers between phrases, but the next scan feels fresh. It's warmth-first, never preachy.

Understand. Tap through to the product detail screen for the flagged ingredients, the full ingredient list, nutrition, and the source citation behind every rule that fired.

Didn't find it? Packaged-food databases are never complete. When a barcode isn't found, Chia flips into a contribute flow: snap up to three label photos (front / ingredients / nutrition), and Google Gemini vision OCR extracts structured fields for you to confirm. Your submission is instantly available to the next person who scans it.

<p><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/shots.dark.svg" /><img src="docs/brand/title/shots.svg" height="32" align="absmiddle" alt="Screenshots" /></picture></p>

<!-- Drop portrait PNGs in docs/screenshots/ ; filenames below are the wired paths. -->

Screens are being captured; they will land here shortly.

<!-- Real captures pending. Drop portrait PNGs (~1080x2340) into docs/screenshots/ then uncomment:
<table>
  <tr>
    <td align="center" width="33%"><img src="docs/screenshots/product-detail.png" alt="Product detail" /><br/><sub>Product detail<br/>flagged ingredients + the cited study behind every rule</sub></td>
    <td align="center" width="33%"><img src="docs/screenshots/history.png" alt="History" /><br/><sub>History<br/>the verdict-rail ledger, grouped by date</sub></td>
    <td align="center" width="33%"><img src="docs/screenshots/contribute.png" alt="Contribute" /><br/><sub>Contribute<br/>snap labels &rarr; Gemini OCR fills the form</sub></td>
  </tr>
</table>
-->

<a id="arch"></a>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/arch.dark.svg" /><img src="docs/brand/title/arch.svg" height="32" align="absmiddle" alt="Architecture" /></picture></summary>

Chia is a client-heavy, offline-first app in front of a serverless edge backend and a self-updating data pipeline. All the fast, private work (scanning, rule evaluation, caching, history) happens on device; the edge exists only to normalize and merge open food data. No third-party API is ever touched directly from the client.

```mermaid
flowchart TB
    User([User scans barcode]):::user

    subgraph Client["Client · React Native + Expo"]
        Scanner["CompactScanner · expo-camera<br/>240px viewfinder"]:::client
        Verdict["VerdictBadge / VerdictSticker<br/>4 signals: color + icon + text + haptic"]:::client
        Eval["HealthEvaluator<br/>custom synchronous rule engine"]:::client
        Rules["defaultRuleset.json<br/>65 block rules"]:::client
        subgraph LocalCache["Local cache-first layer"]
            MMKV["MMKV hot cache<br/>last scan, prefs"]:::client
            SQLite["expo-sqlite<br/>products_cache 7d TTL + scan history"]:::client
        end
        Contribute["Contribute flow<br/>3 photo slots + form"]:::client
    end

    subgraph Edge["Edge · Cloudflare Workers · Hono"]
        WLookup["GET /api/product/:barcode"]:::edge
        WAlt["GET /api/alternatives/:category"]:::edge
        WExtract["POST /api/contribute/extract · OCR"]:::edge
        WContribute["POST /api/contribute"]:::edge
        WUpload["POST /api/contribute/upload-url"]:::edge
        KV["Cloudflare KV<br/>found 14d · categories 1d · rate limits"]:::edge
        Merge["mergeBulkSources<br/>USDA-preferred precedence"]:::edge
        Gemini["Google Gemini 2.5 Flash-Lite<br/>vision OCR"]:::external
    end

    subgraph Data["Data · Supabase Postgres + Storage"]
        OFF[("products_off<br/>Open Food Facts bulk")]:::data
        USDA[("products_usda<br/>USDA Branded Foods")]:::data
        Community[("community_products<br/>user contributions · RLS")]:::data
        Storage["Storage bucket<br/>community-contributions · public"]:::data
    end

    subgraph Pipeline["Pipeline · GitHub Actions"]
        SyncOFF["sync-off.yml · weekly Tue<br/>DuckDB Parquet ingest"]:::pipe
        SyncUSDA["sync-usda.yml · Apr + Oct<br/>stream-json ingest"]:::pipe
        HF["Open Food Facts<br/>Hugging Face Parquet 4.4GB"]:::external
        FDC["USDA FoodData Central<br/>Branded Foods JSON ~3GB"]:::external
    end

    User -->|barcode string| Scanner
    Scanner -->|normalized barcode| MMKV
    MMKV -->|miss| SQLite
    SQLite -->|"miss · network fetch"| WLookup
    WLookup -->|check| KV
    KV -->|"miss"| OFF
    KV -->|"miss"| USDA
    OFF --> Merge
    USDA --> Merge
    Merge -->|"L3 fallback"| Community
    Merge -->|write 14d| KV
    WLookup -->|ChiaProduct + editableByYou| SQLite
    SQLite -->|product| Eval
    Rules --> Eval
    Eval -->|"pass / fail + triggered rules"| Verdict

    Verdict -.->|"not_found / incomplete"| Contribute
    Contribute -->|label photo| WUpload
    WUpload -->|signed URL| Storage
    Contribute -->|PUT JPEG direct| Storage
    Contribute -->|"path + role"| WExtract
    WExtract -->|base64 image| Gemini
    Gemini -->|structured fields| WExtract
    Contribute -->|"name + ingredients + nutrition"| WContribute
    WContribute -->|upsert| Community
    WContribute -->|bust cache| KV

    WAlt -->|category slug| OFF

    HF --> SyncOFF
    FDC --> SyncUSDA
    SyncOFF -->|batch upsert 1000/chunk| OFF
    SyncUSDA -->|batch upsert 1000/chunk| USDA

    classDef user fill:#f5e6d3,stroke:#c9a86a,color:#4a3d2a
    classDef client fill:#e8f0e3,stroke:#7a9b6e,color:#2f4028
    classDef edge fill:#e3ecf5,stroke:#6e88b0,color:#28374a
    classDef data fill:#f0e3ec,stroke:#a86e94,color:#4a2840
    classDef pipe fill:#f5f0e0,stroke:#b0a06e,color:#4a4228
    classDef external fill:#ececec,stroke:#999999,color:#333333
```

The five pillars:

- Offline-first, cache-first. Every previously scanned product keeps working with no network. Lookup falls through three layers (MMKV hot cache ~0ms → SQLite `products_cache` 7-day TTL ~5-10ms → Cloudflare Worker), and all rule evaluation runs locally.
- Serverless edge backend. A Hono Worker on Cloudflare is the only thing that talks to Open Food Facts, USDA, or Gemini. It's fail-closed by design: a missing secret returns `503` for that endpoint, so a deploy without secrets can never expose an unauthenticated write.
- Self-updating data pipeline. GitHub Actions cron jobs keep the food database fresh with a weekly DuckDB-powered Open Food Facts sync and a biannual streaming USDA sync, all with zero manual intervention.
- Deterministic, explainable rule engine. A custom synchronous evaluator matches products against a 65-rule set where every rule cites a primary regulatory document or peer-reviewed paper. No black box, no LLM guessing your health.
- Crowdsourced OCR contributions. When a product is missing, users can add it with label photos; Gemini vision turns pixels into validated, structured data, and the submission seeds all cache layers instantly.

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/scan.dark.svg" /><img src="docs/brand/title/scan.svg" height="32" align="absmiddle" alt="How a scan works" /></picture></summary>

<details>
<summary>Sequence diagram: the full scan → verdict path</summary>

```mermaid
sequenceDiagram
    actor U as User
    participant C as CompactScanner
    participant Cache as MMKV + SQLite
    participant W as CF Worker /api/product
    participant KV as Cloudflare KV
    participant DB as Supabase Postgres
    participant E as HealthEvaluator
    participant V as VerdictBadge

    U->>C: point camera at barcode
    C->>Cache: lookup barcode
    alt cache hit (offline-capable)
        Cache-->>E: ChiaProduct
    else cache miss
        Cache->>W: GET /api/product/:barcode
        W->>KV: check product:v3 key
        alt KV hit
            KV-->>W: cached product
        else KV miss
            W->>DB: read products_off + products_usda
            DB-->>W: bulk rows
            W->>W: mergeBulkSources (USDA-preferred)
            opt bulk miss
                W->>DB: read community_products
            end
            W->>KV: write found product (14d TTL)
        end
        W-->>Cache: ChiaProduct + editableByYou
        Cache-->>E: ChiaProduct
    end
    E->>E: match 65 rules + allergen filters
    E-->>V: verdict pass/fail + triggered rules
    V->>U: color + leaf icon + phrase + haptic
    V->>Cache: record scan to SQLite history
```

</details>

1. The scanner reads and normalizes a barcode and hands it to the lookup pipeline.
2. MMKV → SQLite → Worker: the first cache hit wins. A hit means an instant, fully-offline verdict.
3. On the edge, the Worker checks its 14-day KV cache, then reads `products_off` and `products_usda` in parallel and merges them (USDA-preferred), falling back to `community_products`. A `not_found` is never cached, so a contribution shows up on the very next scan.
4. Back on device, `HealthEvaluator` matches the product against 65 rules plus your allergen filters and resolves a verdict.
5. The verdict fires with color + leaf icon + phrase + haptic, and the scan is UPSERTed into local history.

The verdict state machine (`deriveVerdict`) collapses lookup status + evaluation result + a data-sparse flag into one of 8 UI states: `pass`, `fail`, `unknown`, `scanning`, `not_found`, `incomplete`, `error_network`, `error_eval`, so every dead end has an honest, designed screen instead of a spinner.

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<a id="eng"></a>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/eng.dark.svg" /><img src="docs/brand/title/eng.svg" height="32" align="absmiddle" alt="Engineering highlights" /></picture></summary>

The things a strong engineer notices when they read past the screenshots:

- Explainable rules grounded in real literature. The 65-rule set (`ruleset v1.2`) is curated exclusively from primary sources: the NTP Report on Carcinogens, WHO IARC monographs, McCann et al., Lancet 2007 (food dyes and hyperactivity), Hazen et al., Nature Medicine 2023 (erythritol and cardiovascular risk), and more. Every rule carries its citation into the UI. A product fails if any triggered rule matches or a product allergen matches your filters, and allergen matches are a hard fail that can't be whitelisted.

- A rule engine that was rewritten for the right reasons. `json-rules-engine` was removed and replaced with a custom synchronous evaluator, cutting ~250KB off the bundle, with `RegExp` patterns pre-compiled once per ruleset and cached (O(N) over rules, zero per-scan allocation). Rules match on two facts (`additivesTags` E-numbers, `ingredientsText`) with two operators (`contains`, case-insensitive `matchesRegex`).

- USDA-over-Open-Food-Facts precedence merge. When both sources have a product, USDA wins for nutrition numerics, name, brand, ingredients, categories, and serving size; Open Food Facts fills in `imageUrl`, additives, allergens, Nutri-Score, and NOVA group. A USDA-measured `0` stays `0` rather than being overwritten by a crowdsourced estimate, and USDA's ALL-CAPS bulk text is title-cased while preserving real acronyms (USDA, HFCS, BHT).

- Offline-first data layer with careful cache invalidation. Found products get a 7-day `staleTime`; `not_found` results use `staleTime: 0`, so a contributor's re-scan refetches immediately and shows their submission. A successful contribution seeds all three cache layers at once to kill any stale-data race on the detail screen.

- Anonymous auth done right. The client sends a raw device UUID; the Worker HMAC-SHA256 hashes it (with a salt) before any DB write, so only hashes are ever stored. Re-hashing the requester on read computes an `editableByYou` flag, and the same hash guards photo-upload paths against cross-contributor tampering.

- Security posture. Row-Level Security on every Postgres table (public `SELECT` on bulk tables; service-role-only writes to community data and Storage). Per-IP rate limits (100 req/min global, a separate 10 req/min bucket for contributions). CORS is scoped to the specific methods and headers the app uses; origins are open by design, since Chia's product lookups are a public read API.

- iOS 26 "Liquid Glass" design system. A bespoke glass primitive (`expo-glass-effect`) with 5 material variants and a BlurView + sheen fallback for older iOS, driven entirely by design tokens in `theme/tokens.ts`, with no raw hex and no magic spacing. NativeTabs, Nunito display + Inter body, custom SVG leaf glyphs, and a die-cut verdict "sticker."

- Accessibility baked into the core contract. Verdicts never rely on color alone: color + icon + text + haptic, always, enforced as a component contract.

- TypeScript strict, zero `any`. `any` is forbidden codebase-wide; `unknown` + type guards instead. Pre-commit hooks (Husky + lint-staged) run lint-staged, `tsc` typecheck, and `jest --ci` on every commit.

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<a id="stack"></a>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/stack.dark.svg" /><img src="docs/brand/title/stack.svg" height="32" align="absmiddle" alt="Tech stack" /></picture></summary>

<p align="center">
  <img src="https://skillicons.dev/icons?i=ts,js,react,nodejs,githubactions,cloudflare,supabase,postgres,jest&perline=15" height="48" alt="TypeScript, JavaScript, React, Node.js, GitHub Actions, Cloudflare, Supabase, Postgres, Jest" />
</p>

| Layer | Tools |
| --- | --- |
| App runtime | React Native 0.85.3 · Expo SDK 56 · React 19.2.3 · New Architecture + React Compiler |
| Language | TypeScript 6.0.3 (strict, zero `any`) for the app · TypeScript 5.9.2 for the workers |
| Navigation & UI | expo-router NativeTabs · react-native-reanimated 4.3.1 + gesture-handler · `expo-glass-effect` (iOS 26 Liquid Glass, 5 variants) · react-native-svg · Nunito + Inter |
| State & data | Zustand 5.0.14 (2 stores) · TanStack Query 5.100.14 (MMKV-persisted) · react-native-mmkv 4.3.1 · expo-sqlite |
| Edge backend | Cloudflare Workers · Hono 4.6.0 · Wrangler 4.0.0 · Cloudflare KV |
| Data & storage | Supabase Postgres (3 tables, RLS everywhere) · Supabase Storage · Google Gemini 2.5 Flash-Lite (OCR) |
| Pipeline | GitHub Actions cron · DuckDB (Open Food Facts) · stream-json (USDA) |
| Testing & quality | Jest 29.7.0 + @testing-library/react-native (app) · Vitest 2.1.0 (workers) · ESLint 9.25.0 (React Compiler / react-hooks v7) · Husky + lint-staged 17 |

<details>
<summary>Data pipeline, in numbers</summary>

- Open Food Facts, weekly (Tuesday 06:07 UTC). Downloads a 4.4 GB Parquet from Hugging Face, uses DuckDB column-projection filtered to US + CA, batch-upserts in 1,000-row chunks. A recorded run upserted 869,937 rows in 442 seconds.
- USDA Branded Foods, biannual (Apr 16 + Oct 16, 07:23 UTC). Stream-parses a ~3 GB JSON at ~245 rows/sec (~2.5 hours), batch-upserts in 1,000-row chunks.
- Both prune rows older than 365 days to drop delisted products, with aggressive autovacuum tuning to survive the upsert storms.
- OCR runs on Gemini 2.5 Flash-Lite, temperature 0.1, role-specific JSON schemas (front / ingredients / nutrition), numeric outputs bounded to drop hallucinations.

</details>

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/testing.dark.svg" /><img src="docs/brand/title/testing.svg" height="32" align="absmiddle" alt="Testing & quality" /></picture></summary>

Chia is built like a product, not a prototype.

- 30 test files (20 app Jest suites + 8 worker Vitest suites + 2 sync-script suites) with 400+ test cases (251 app + 156 worker) across ~26 UI components.
- No-throw data layer. Every scan-history function is failure-tolerant: reads return `[]` on error, writes swallow exceptions, so a corrupt SQLite state can't crash the scan loop.
- Pinned behavior. Verdict phrases, the 200-row history prune, and the UPSERT-on-barcode dedup are all asserted in tests, so accidental drift fails loudly in CI.
- Every commit is gated by lint → typecheck → tests via Husky, with ESLint wired to the React Compiler / react-hooks v7 rule set.
- The workers are their own world: separate TypeScript version, separate Vitest suite, separate deploy, so the edge can evolve without destabilizing the app.

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<a id="roadmap"></a>

<details>
<summary><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/roadmap.dark.svg" /><img src="docs/brand/title/roadmap.svg" height="32" align="absmiddle" alt="Roadmap" /></picture></summary>

Honest, forward-looking, and clearly planned, not shipped:

- Allergen preferences UI. The hard-fail allergen evaluation already exists in the engine; this exposes it in Settings and on the detail screen.
- Healthier alternatives. Surface better products when something fails (the `/api/alternatives/:category` Worker endpoint is already live).
- Instant photo verdict on unknown barcodes. Run OCR plus the local rule engine on a label photo to give a verdict even when a barcode isn't in the database.
- Settings buildout. The tab is currently a stub (Allowed ingredients / Account / About marked "Coming soon").
- Animated product-image fallbacks and further product-detail polish.
- Monetization. An OCR usage gate is already scaffolded on the edge (currently disabled).

</details>

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/ui/rule.dark.svg" /><img src="docs/brand/ui/rule.svg" width="86%" alt="" /></picture></p>

<a id="more"></a>

<p><picture><source media="(prefers-color-scheme: dark)" srcset="docs/brand/title/more.dark.svg" /><img src="docs/brand/title/more.svg" height="32" align="absmiddle" alt="Let's talk" /></picture></p>

<p align="center">
  <img src="docs/brand/sig.svg" width="150" alt="SK monogram" />
</p>

<p align="center">Currently exploring how agentic AI changes what a single quality engineer can own.</p>

<p align="center">Chia is a solo-built project in active development. The source is private, but I'd love to show it off. Live walkthrough or TestFlight build, just ask.</p>

<p align="center">
  <a href="https://www.linkedin.com/in/kucherko/"><img src="https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:vkucherko7@gmail.com"><img src="https://img.shields.io/badge/Email_me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</p>
