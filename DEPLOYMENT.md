# Deployment Checklist

## Current status

This standalone repo is prepared for Netlify deployment, but no live deployment is claimed until the Netlify site is recreated and verified.

## Create GitHub repo

Create an empty GitHub repository:

```text
Dreamwav3/movingoutcosts
```

Do not add README, `.gitignore`, or license on GitHub because this local repo already has files.

Then connect and push from this folder:

```bash
git remote add origin https://github.com/Dreamwav3/movingoutcosts.git
git push -u origin main
```

## Create Netlify site

In Netlify, create a new site from Git:

| Setting | Value |
|---|---|
| Repository | `Dreamwav3/movingoutcosts` |
| Branch | `main` |
| Base directory | leave blank |
| Build command | leave blank |
| Publish directory | `.` |

Because this is a standalone repo, Netlify should not inherit SellerMath settings.

## Verify after first deploy

Check these URLs:

- `/`
- `/move-out-cleaning-cost-estimator/`
- `/security-deposit-deduction-checklist/`
- `/apartment-move-out-cleaning-checklist/`
- `/apartment-move-out-timeline/`
- `/robots.txt`
- `/sitemap.xml`

The homepage title should be:

```text
Moving-Out Cost & Deposit Checklist | Plan Cleaning, Supplies & Deposit Prep
```

It should not say SellerMath.

## Post-deploy crawl-file fix

After the real live URL exists:

1. Replace all `https://example.com/moveout-placeholder` URLs in `sitemap.xml`.
2. Add `Sitemap: https://LIVE-URL/sitemap.xml` to `robots.txt`.
3. Commit and push.
4. Re-check live `robots.txt` and `sitemap.xml`.
