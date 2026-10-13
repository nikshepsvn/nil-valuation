# NIL Valuation Lab

A single-file scenario model for Nillion ($NIL): what the token could be worth if Covenants seal a share of onchain order flow.

- Loads the live price from CoinGecko, and live Covenant, stake and node counts from Ethereum mainnet. If those fail, it falls back to a 13 Oct 2026 snapshot.
- Saves every model setting in the URL hash, so a scenario can be shared as a link.
- Has no build step and no dependencies apart from Google Fonts.

## Deploy on GitHub Pages

```bash
git init && git add . && git commit -m "feat: NIL valuation lab"
gh repo create nil-valuation --public --source . --push
gh api -X POST repos/{owner}/nil-valuation/pages -f "source[branch]=main" -f "source[path]=/"
```

The site will be at `https://<user>.github.io/nil-valuation/`. Netlify Drop, Vercel or any static host also works: upload `index.html`.

## Updating the numbers

The snapshot values are in the `S`, `FLOWS`, `MULTS` and `PEERS` constants at the top of the `<script>` block in `index.html`.
