# Sources and Compilation Notes

## Method

Each part family was compiled from three classes of source, in this order:

1. **OEM parts manuals** — part numbers, item positions, build-date splits, model coverage.
2. **Distributor catalogs** — specifications, interchange tables, availability observations.
3. **Component-maker documentation** — where the fryer brand relabels a third-party device (Robertshaw, Fenwal, EGO), the maker's own specification was used.

Where the three disagreed, the disagreement is recorded rather than resolved silently. Two examples currently in the dataset:

- A 24 V gas valve regulator set point published as both 3.0 in WC and 3.5 in WC.
- A discontinued hi-limit superseded by a part with a sensing bulb 3/8 in shorter than the original.

## Cross-reference reliability

Interchange numbers in `cross-reference.csv` come from distributor tables, not from manufacturer statements. They are recorded as **reported**, not **verified**. Treat them as leads.

## Availability observations

Availability statements, where present on the reference site, are point-in-time observations recorded with a check date. They are not commitments and are not mirrored in this dataset.

## Licensing of the underlying data

Part numbers and specifications are facts and are reproduced as published by their respective sources. Brand and product names are trademarks of their respective owners. This repository is not affiliated with, endorsed by or sponsored by any equipment manufacturer.

## Corrections

If a row is wrong, the useful correction includes the number, the field, the value you believe is correct, and the document that establishes it. Corrections without a source cannot be evaluated.
