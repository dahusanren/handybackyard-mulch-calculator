# Mulch Calculator

A free, dependency-free mulch volume calculator: cubic yards, 2 cu ft and 3 cu ft bag counts, and coverage depth for a rectangular garden bed.

Runs entirely in the browser — no signup, no build step, no tracking script, no network calls.

**Live tool:** https://handybackyard.com/mulch-calculator

## Why it is open source

The [awesome-agriculture](https://github.com/brycejohnston/awesome-agriculture) maintainer asked whether this project is open source. It is — at least this part of it. The arithmetic that was previously only readable on the live page is written out here so you can check it yourself.

## The math

Three numbers in: bed length (feet), bed width (feet), mulch depth (inches).

```
cubic feet = length (ft) × width (ft) × depth (in) ÷ 12
cubic yards = cubic feet ÷ 27
2 cu ft bags = cubic feet ÷ 2, rounded UP
3 cu ft bags = cubic feet ÷ 3, rounded UP
```

Depth is entered in inches, so it is divided by 12 before it is multiplied by anything else. Bag counts are rounded **up**: running short partway along a border costs more than one spare bag in the garage.

Add roughly 10% for waste.

### Worked example — 20 ft × 10 ft bed at 3 inches

| Quantity | Value |
|---|---|
| Area | 200 sq ft |
| Cubic feet | 20 × 10 × 3 ÷ 12 = **50** |
| Cubic yards | 50 ÷ 27 = **1.85** |
| 2 cu ft bags | 50 ÷ 2 = **25** |
| 3 cu ft bags | 50 ÷ 3 = 16.67 → **17** |

The same bed at other depths:

| Depth | Cubic feet | Cubic yards | 2 cu ft bags |
|---|---|---|---|
| 2 in | 33.33 | 1.23 | 17 |
| 3 in | 50 | 1.85 | 25 |
| 4 in | 66.67 | 2.47 | 34 |

## Depth guidance

Extension services commonly advise no more than 2 to 3 inches of fine-textured mulch such as compost and bark on beds, and shallower depths around trees and shrubs, where a thick layer holds moisture against the trunk. Check your local guidance before picking a depth.

## Sources

- [Clemson Cooperative Extension — Mulch](https://hgic.clemson.edu/factsheet/mulch/)
- [University of Maryland Extension — Mulching Trees and Shrubs](https://extension.umd.edu/resource/mulching-trees-and-shrubs/)

## Use it

Open `index.html` in any modern browser — there is no build step. To embed it on your own page, use an `<iframe>`:

```html
<iframe src="https://handybackyard.com/embed/mulch-calculator"
        width="100%" height="620" loading="lazy"
        title="Mulch calculator"></iframe>
```

## License

MIT — see [LICENSE](LICENSE).
