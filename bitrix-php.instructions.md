---
applyTo: "**/*.php"
---

## PHP tags
- Use short echo tag `<?=` instead of `<?php echo`.
- Use full `<?php` tag for logic blocks (conditions, loops, function calls).
- Never use short open tag `<?` alone (without `=`).
- No spaces after `<?=` and before `?>`: `<?=$Product['NAME']?>`

## Bitrix PHP Variable Naming Conventions

### Variable name suffixes

Variables storing Bitrix entities should use these suffixes:
- `*Element` — infoblock element: `$lstElements`, `$dctElement`
- `*Product` — catalog product (item or offer with price): `$refProducts`
- `*Offer` — catalog offer (SKU): `$lstOffers`
- `*Good` — product with offers: `$dctGood`
- `*Section` — infoblock section: `$lstSections`
- `*Deal` — CRM deal: `$dctDeal`
- `*Company` — CRM company: `$refCompanies`
- `*Contact` — CRM contact: `$lstContacts`
- `*Lead` — CRM lead: `$dctLead`
- `*User` — user: `$refUsers`
- `*Order` — order: `$dctOrder`
- `*Price` — price: `$Price` (scalar) or `$lstPrices` (array)
- `*Filter` — DB filter array: `$dctFilter`

## HTML data attributes for Bitrix entities

Use pattern: `data-bx-{module}-{entity}-{field}`

### Standard modules
- Infoblock section ID: `data-bx-iblock-section-id="123"`
- Infoblock element ID: `data-bx-iblock-element-id="456"`
- Infoblock element code: `data-bx-iblock-element-code="my_product"`
- CRM deal ID: `data-bx-crm-deal-id="789"`

### Custom entities
- Use `app` as module name: `data-bx-app-{entity}-{field}`
- Or use `orm` with table name: `data-bx-orm-{table}-{field}`
- Note: `orm` pattern exposes database table names in HTML (usually not a security risk, but may be undesirable)