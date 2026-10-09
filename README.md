# Las Vegas Hotel Resort Fees

A machine-readable dataset of nightly resort fees charged by Las Vegas hotels, compiled from the hotels' official pages and the site's own verification passes. It covers 27 properties on and around the Las Vegas Strip, with both pre-tax and tax-inclusive figures.

This dataset powers the comparison table at https://theresortfee.com/, where each figure is also published with its verification date and sources.

## Files

- `las-vegas-resort-fees.csv` — the dataset (UTF-8, comma-separated, header row included)

## Columns

| Column | Meaning |
|---|---|
| `hotel` | Hotel name as listed by the property |
| `resort_fee_usd` | Nightly resort fee in USD, before tax |
| `resort_fee_with_tax_usd` | Nightly resort fee in USD, including the 13.38% Las Vegas lodging tax |
| `year_verified` | Season the figure was verified for (figures are re-checked each season; 2026 rows are confirmed for the 2026 season) |
| `source_type` | How the figure was sourced; blank where not recorded in this export |

## Usage

```python
import csv

with open('las-vegas-resort-fees.csv') as f:
    for row in csv.DictReader(f):
        print(row['hotel'], row['resort_fee_with_tax_usd'])
```

## Freshness

Last updated: 2026-10-09. Resort fees change; 2026-season rows are confirmed for 2026, older rows are carried over from the previous verification pass and are being re-checked hotel by hotel.

## License

Released under CC0 1.0 Universal — use it for anything, no attribution required (though a link back is appreciated).
