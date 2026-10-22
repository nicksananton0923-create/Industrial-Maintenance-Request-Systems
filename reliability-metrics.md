# Reliability Metrics — Industrial Electrical Maintenance and Breakdown Analysis

## MTBF, MTTR, Availability

See Project 09's `procedures/reliability-metrics-calculation.md` for the calculation methodology. The same calculation applies here, using `breakdown-record.csv` as input.

## Worked Example (fictional)

For asset ELE-003 (Motor M1) over 12 months with 1 breakdown:

```
Total operating time = 365 × 24 - 6 (downtime) = 8754 hours
Number of breakdowns = 1
MTBF = 8754 / 1 = 8754 hours
MTTR = 6 / 1 = 6 hours (downtime only; total repair time including sourcing parts may be longer)
Availability = 8754 / (8754 + 6) = 0.9993 = 99.93%
```

## Industry Benchmarks

Typical industry benchmarks for electrical equipment reliability:

| Asset class | MTBF (hours) | Availability (%) |
|---|---|---|
| LV switchgear | 100,000+ | 99.99+ |
| MV switchgear | 50,000+ | 99.95+ |
| Distribution transformer | 100,000+ | 99.95+ |
| LV motor | 50,000+ | 99.5+ |
| VFD | 30,000+ | 99.0+ |
| UPS (excluding battery) | 50,000+ | 99.95+ |

(Benchmarks are indicative; actual values depend on operating conditions and maintenance quality.)
