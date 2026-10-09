# Readiness index

For each service area (zone), the weekly index is a number from 0 to 100:

```
index = 0.30 × coverage
      + 0.20 × credentials
      + 0.15 × response
      + 0.20 × condition
      + 0.15 × backlog
```

| Factor | How to calculate it (0 to 100) |
|---|---|
| Coverage | Number of supervisors based in the area: 0 → 0, 1 → 60, 2 → 85, 3 or more → 100 |
| Credentials | Share of the area's supervisors' certificates that are still valid on the reference date |
| Response | 100 minus (median first-response minutes − target) × penalty, limited to 0–100. Suggested target 30 minutes and penalty 1.2 per minute |
| Condition | Share of the area's sites whose status is `OK` |
| Backlog | 100 minus 20 for each overdue work order in the area, minimum 0 |

The company-wide index is the average of the areas weighted by the number of sites in each.

## Reading it

- 75 or more: ready. 55 to 74: watch. Below 55: act this week.
- Start with the lowest area, then look at its weakest factor.
- Compare week to week. The trend matters more than a single number.

## Adjusting it

The weights, targets and penalties are a starting point. Write down any change and apply it to the baseline as well, so that comparisons stay fair.
