# Motorcycle CAP spreadsheet

This document describes a Google Sheets workbook for calculating the motorcycle CAP indexes used in the _The perfect bike_ post.

Each index is threshold-normalised:

- `C >= 1` means Comfortable
- `A >= 1` means Affordable
- `P >= 1` means Performant

## Sheet Columns

Use these columns.

| Column | Name | Notes |
|---|---|---|
| A | Brand | Manufacturer |
| B | Model | Model name |
| C | Variant | Trim/variant |
| D | Year | Model year |
| E | C | Comfort index; formula |
| F | A | Affordability index; formula |
| G | P | Performance index; formula |
| H | Price | New purchase price |
| I | GDP per capita | Local GDP per capita in the same currency as price |
| J | Inflation index | Use `1` for current prices |
| K | Adjusted price | Formula |
| L | Horsepower | Manufacturer horsepower figure |
| M | Wet weight (kg) | Wet/kerb weight |
| N | Lean angle (degrees) | Best available figure |
| O | Advanced suspension | `1` if true, otherwise `0` |
| P | Double front disc | `1` if true, otherwise `0` |
| Q | Tall windscreen | `1` if true, otherwise `0` |
| R | Additional weather protection | `1` if true, otherwise `0` |
| S | Luggage support | `1` if true, otherwise `0` |
| T | Luggage included | `1` if true, otherwise `0` |
| U | Range > 300km | `1` if true, otherwise `0` |
| V | Range > 500km | `1` if true, otherwise `0` |
| W | Upright position | `1` if true, otherwise `0` |
| X | Cruise control | `1` if true, otherwise `0` |
| Y | Top case | `1` if true, otherwise `0` |
| Z | Backrest and armrests | `1` if true, otherwise `0` |

## Comfort Scoring

Every comfort field is a 1-point boolean. Enter `1` if the bike has the property, and `0` if it does not.

- Tall windscreen
- Additional weather protection
- Luggage support
- Luggage included
- Range > 300km
- Range > 500km
- Upright position
- Cruise control
- Top case
- Backrest and armrests

These booleans are cumulative. A bike with more than 500 km of range also has more than 300 km of range, so both fields should be `1`. A bike with factory luggage included usually also has luggage support, so both fields may be `1` when both statements are true.

The comfort threshold is 5 points.

## Formulas

Put these formulas in row 2 and fill down.

### Adjusted Price

Cell `K2`:

```text
=H2/J2
```

For current bikes, set `J2` to `1`.

For older bikes, use an inflation index that converts the original new price into present-value terms.

### Comfort Index

Cell `E2`:

```text
=SUM(Q2:Z2)/5
```

### Affordability Index

Cell `F2`:

```text
=(0.25*I2)/K2
```

### Performance Index

Cell `G2`:

```text
=IF(N2<35,0,((((L2/M2)*1000)*(N2/45))/350)*(0.8+0.1*O2+0.1*P2))
```

If your Google Sheets locale uses semicolons instead of commas, replace commas in formulas with semicolons.

## Optional CAP Class

If you want a computed class label, add a new column after `Z` with this formula:

```text
=TEXTJOIN(" + ",TRUE,IF(E2>=1,"Comfort",""),IF(F2>=1,"Affordability",""),IF(G2>=1,"Performance",""))
```

## Interpretation

- `C`, `A`, and `P` all below `1`: the bike does not satisfy any CAP axis.
- Exactly one index at or above `1`: single-axis bike.
- Exactly two indexes at or above `1`: valid two-axis compromise.
- All three indexes at or above `1`: either a miracle, a data error, or a bike grading one axis on a curve.

## Notes

- Use wet weight, not dry weight.
- Use manufacturer horsepower when available.
- Lean angle is rarely official. Use the best available source, but keep the same source style across bikes where possible.
- Purchase price is intentionally new-price based. Used bargains do not count.
- Running costs matter, but they are omitted from the index to avoid turning the exercise into investigative journalism.
