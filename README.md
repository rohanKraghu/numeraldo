# numeraldo.org

The Numeraldo website, served by GitHub Pages at [numeraldo.org](https://numeraldo.org).
A static site: no build step, no dependencies, no framework.

```
index.html          Numeraldo, the nonprofit.
crash-course/       Financial Literacy Crash Course (its own README).
assets/             Images and the two social share cards.
og-src/             Source pages for the share cards. Not linked from the site.
CNAME               numeraldo.org. GitHub Pages reads it; leave it alone.
```

## Updating the Numeraldo figures

Every number on the home page renders from one object near the bottom of
`index.html`:

```js
const NUMERALDO = { goal: 25000, lastUpdated: "...", programs: [ ... ] };
```

The hero ledger, the fundraising meter, the allocation table and its
percentages all derive from it. Edit that block and nothing else.

One exception: the share card `assets/og-numeraldo.png` repeats the three
hero figures and is a flat image, so it does not follow. Regenerate it when
they change, as below.

## Social share cards

| Page | Card |
|---|---|
| `index.html` | `assets/og-numeraldo.png` |
| `crash-course/`, all four pages | `assets/og-crash-course.png` |

Each card is drawn by the page of the same name in `og-src/`. To change
one: edit its source, open it in a browser sized to exactly 1200 x 630,
screenshot it, and replace the PNG.

## Domain and email

DNS for numeraldo.org is managed at Business Identity
(`hosting.businessidentity.llc`). The web records point at GitHub Pages:
four A records for the apex (185.199.108.153, .109.153, .110.153,
.111.153) and `www` as a CNAME to `rohankraghu.github.io`. The MX and SPF
records stay with Business Identity, which hosts `info@numeraldo.org`;
do not cancel that plan without moving email first.

Because this repository is named `numeraldo` and has a custom domain,
`rohankraghu.github.io/numeraldo/` redirects here automatically.

## Conventions

- **No em dashes.** Colons, semicolons, commas and brackets instead. En
  dashes are used for ranges.
- **No comments** in HTML, CSS or JavaScript, which is why this file exists.
