# Compliance map

> The compliance agent reads this before passing or failing a draft. It maps sector to the regulators and the hard rules. It is conservative on purpose. Where a specific rule needs checking against the live code, it is marked `[VERIFY]`. This map does not replace a qualified reviewer for regulated content.

Baseline for every Irish or UK client, whatever the sector:

- **ASAI** (Ireland) and **ASA** (UK) advertising codes: legal, decent, honest, truthful. No misleading claims. Substantiate before you publish.
- **GDPR and ePrivacy:** no personal data or customer names in content unless the client has provided and cleared them.
- Claims must be substantiated. If you cannot evidence it, flag it `[VERIFY]`, do not soften and ship.

## Sector rules

| Sector | Regulators and codes | Hard rules (never break) | Reviewer before publish |
|--------|----------------------|--------------------------|-------------------------|
| Investment funds, financial services | Central Bank of Ireland, ASAI, plus the firm's own compliance function | No return, yield or performance projections. Past performance needs the prescribed warning verbatim. No "guaranteed", "safe" or "risk-free". Capital-at-risk warning where relevant. No advice framing. | Always. Qualified compliance sign-off. |
| Healthcare, health products, supplements | ASAI, plus product rules for medicines and food. EU health and nutrition claims rules for food and supplements `[VERIFY]` | No medical claims or implied medical claims. No "cures", "treats", "prevents". No before-and-after promising outcomes. Only use authorised health claims for food. | Always for any health claim. |
| Health insurance | HIA (Ireland), Central Bank of Ireland, ASAI | No comparative claims about named insurers unless authorised. No misleading cover or price claims. Show key terms. | Always. |
| Charity, not-for-profit | Charities Regulator (Ireland), ASAI | Honest use of donations and impact. No overstated outcome claims. Respectful portrayal of beneficiaries with consent. | For fundraising and impact claims. |
| FMCG, food and drink | ASAI, EU food information and health/nutrition claims rules `[VERIFY]` | Only authorised nutrition and health claims. No misleading "natural", "healthy" or origin claims. Alcohol has its own code if relevant `[VERIFY]`. | For any nutrition or health claim. |
| Ecommerce, retail | ASAI, consumer protection and pricing rules `[VERIFY]` | Prices and offers must be accurate with effective dates. No fake scarcity or fake reviews. Show delivery and returns terms where claimed. | For price and offer claims. |
| B2B, services | ASAI, ASA | No unsubstantiated performance or "number one" claims. No comparative claims about named competitors unless authorised. Testimonials must be real and evidenced. | For proof and comparative claims. |
| Publishing, media | ASAI, plus IP and copyright | No uncleared third-party content. Clear labelling of sponsored or affiliate content. | For sponsored and affiliate content. |

## How the compliance agent uses this

1. Identify the sector from the voice pack or the brand folder.
2. Pull the row above plus the client's own `compliance/advertising.md`, `disclosures.md` and `prohibited-claims.md` if they exist. The client's own file wins where it is stricter.
3. Check every claim, number, comparison and call to action against the hard rules.
4. Insert required disclosures verbatim from the client's disclosures file. If a required disclosure is missing, flag it, do not write your own.
5. For any regulated sector, mark the draft "needs qualified reviewer" and list the lines that need sign-off.

If the sector is not listed, default to the baseline plus "treat as regulated and flag for review" until the operator confirms otherwise.
