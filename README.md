# Commercial Fryer Parts — Cross-Reference Dataset

A machine-readable cross-reference dataset for commercial deep-fryer components: thermostats, hi-limits, gas valves, ignition boards, thermopiles and heating elements used on Hobart, Vulcan, Wolf, Garland, Frymaster and Broaster equipment.

Assembled from publicly available OEM parts manuals, distributor catalogs and interchange tables. Provided as a reference for identification and research.

**Full reference site:** https://magenta-puffpuff-d66f59.netlify.app

---

## What is in this repository

| File | Rows | Contents |
|---|---|---|
| `data/part-numbers.csv` | 13 | Primary part numbers with type and brand coverage |
| `data/cross-reference.csv` | 119 | Primary number → interchange number mappings |
| `data/specifications.csv` | 117 | Specification fields per part family (long format) |
| `data/fitment.csv` | 249 | Part number → brand → compatible model |
| `data/comparisons.csv` | 10 | Whether one part can replace another, with the reason |

---

## Coverage

| System | Families | Distinct part numbers |
|---|---|---|
| Thermostats / hi-limits | 7 | 80 |
| Gas valves / ignition / thermopiles | 6 | 52 |
| Heating elements | 3 | — |

Brands covered: Hobart, Vulcan, Wolf, Garland, Frymaster, Broaster, Welbilt, plus Robertshaw and Fenwal component-level equivalents.

---

## Data model

### `part-numbers.csv`
```
part_number, type, brands, cross_ref_count, reference_page
```

### `cross-reference.csv`
One row per interchange number. `primary_part_number` is the number the page is organised around; `interchange_number` is every number reported to correspond to it.

**Important:** interchange numbers come from distributor tables, not from manufacturer statements. A mapping is a claim about compatibility, not a verification of it.

### `specifications.csv`
Long format — one row per field, so families with different fields stay in one table without sparse columns.

### `fitment.csv`
One row per (part, brand, model). Model strings are reproduced as published; some are series names rather than single model codes.

### `comparisons.csv`
`part_a`, `part_b`, the question a buyer asks, a short answer, and the reason. This is the highest-value subset: whether a substitute is safe.

---

## What this dataset is not

- **Not an offer, quotation or availability statement.** No row implies a part is in stock at any seller at any price.
- **Not a manufacturer publication.** Every cross-reference is reproduced as reported by a distributor or catalog.
- **Not a fitment guarantee.** Physical fit does not establish functional equivalence — especially for safety devices.
- **Not complete.** Fields marked as not published were genuinely absent from the sources checked.

---

## How to use it responsibly

1. **Verify against the equipment's own parts manual** before ordering anything.
2. **Treat interchange tables as leads, not answers.** If a mapping does not state the dimensions that matter (bulb size, capillary length, reset type, fitting thread), it has not been verified at the level that matters.
3. **Never substitute a safety device on physical fit alone.** A hi-limit that is dimensionally close but has the wrong reset behaviour removes a protection layer.

---

## Related reference

The site at **https://magenta-puffpuff-d66f59.netlify.app** expands each part number into a full page: specifications, cross-references, compatible models, availability observations, and a "what to verify before ordering" list. It also carries part-number comparisons and longer guides on how this parts market works.
