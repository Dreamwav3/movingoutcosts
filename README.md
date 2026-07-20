# MoveOutMath / Moving-Out Cost & Deposit Checklist

Static mini-site for renters planning move-out costs, cleaning, deposit documentation, and apartment move-out timelines.

## What this repo is

This is the **standalone deploy repo** for the Moving-Out Cost & Deposit Checklist site.

It was exported from the master portfolio workspace:

`/home/dreamz/Documents/Projects/mini-businesses/projects/moving-out-cost-deposit-checklist/site/public`

The master portfolio repo stays as the planning/source-of-truth workspace. This repo exists so Netlify can deploy this site cleanly without being affected by the SellerMath `netlify.toml` in the master repo.

## Pages

- `/` — main moving-out cost and deposit checklist calculator
- `/move-out-cleaning-cost-estimator/`
- `/security-deposit-deduction-checklist/`
- `/apartment-move-out-cleaning-checklist/`
- `/apartment-move-out-timeline/`
- `/robots.txt`
- `/sitemap.xml`

## Local preview

From this folder:

```bash
python3 -m http.server 8000
```

Open:

```text
http://127.0.0.1:8000/
```

## Netlify deployment

Recommended Netlify setup:

| Setting | Value |
|---|---|
| Repository | `Dreamwav3/movingoutcosts` |
| Branch | `main` |
| Base directory | leave blank |
| Build command | leave blank |
| Publish directory | `.` |

This repo also includes a minimal `netlify.toml`:

```toml
[build]
  publish = "."
  command = ""
```

## After Netlify gives the live URL

Before calling the site fully launched:

1. Replace `https://example.com/moveout-placeholder` in `sitemap.xml` with the real production base URL.
2. Add a real sitemap line to `robots.txt`:

```text
Sitemap: https://YOUR-LIVE-URL/sitemap.xml
```

3. Commit and push those URL updates.
4. Verify all live pages return HTTP 200.
5. Verify the homepage calculator still works.

## Guardrails

- Do not add fake product/payment links.
- Do not claim guaranteed security-deposit return.
- Keep copy educational and estimate-based.
- The free tool should remain useful without a paid product.
