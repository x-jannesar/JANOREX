# JANORÉX independent language websites

This directory is additive; the original JANORÉX root website is unchanged. Do not use the GitHub subdirectory URLs as independent production websites.

## Production architecture (Cloudflare Pages Free)

Each language's directory is **one separate Cloudflare Pages project** with its own root hostname (e.g. `your-unique-name.pages.dev`). The hostname examples below are unclaimed suggestions, NOT published sites:

| Locale | GitHub source directory | Suggested project name (availability unverified) |
| --- | --- | --- |
| Persian | `sites/fa` | `janorex-persian` |
| English | `sites/en` | `janorex-english` |
| Arabic | `sites/ar` | `janorex-arabic` |

## Cloudflare connection setup

1. Create or sign in to a free Cloudflare account. Navigate to **Workers & Pages > Create application > Pages > Connect to Git**.
2. Authorize the `x-jannesar/JANOREX` repository.
3. Create **three separate** Pages projects from the same repository. For each, choose its own project name, select the **main** branch, then set **Root directory** to `sites/fa`, `sites/en` or `sites/ar` respectively.
4. For plain HTML, use Build command `exit 0` and Build output directory `.` within the selected root directory.
5. Deploy and verify the **production** `<project-name>.pages.dev` host, accessible without login, responds 200, and is not blocked by a noindex header or robots rules.
6. After the actual project names are allocated, insert each site's verified absolute HTTPS URL in its own canonical metadata, WebSite JSON-LD and sitemap.xml. Never use a different site's URL as canonical.
7. Verify each separate URL-prefix property in Google Search Console, submit its own sitemap and monitor indexing. Indexing is Google-controlled, not guaranteed.
8. Configure **Build watch paths** to include only the particular site's `sites/<language>/**` directory to prevent every push from building every project; free Pages Git builds have a 500/month quota.

### Important safeguards

- Cloudflare Pages currently documents a limit of **100 Pages projects per account**. Check any preexisting projects in the account before planning all 100.
- Hostnames are **subdomains of pages.dev**, not 100 separately registered top-level domains.
- Avoid mass-publication of near-duplicate, low-value or unreviewed translations. Expand by language only when meaningful human-reviewed localized copy and assets are ready.
- No false testimonials, clinical results, or certifications. Do not edit the preexisting root site without a separate decision.

Sources: https://developers.cloudflare.com/pages/platform/limits/ ; https://developers.cloudflare.com/pages/configuration/monorepos/ ; https://developers.cloudflare.com/pages/framework-guides/deploy-anything/ ; https://developers.google.com/search/docs/appearance/site-names
