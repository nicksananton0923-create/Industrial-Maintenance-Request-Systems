# Logic and Operation — Industrial Electrical Maintenance and Breakdown Analysis

## PM Schedule Logic

Each PM task has an interval (months, run-hours, or operations) and a last-completed date. The next-due date is computed by adding the interval to the last-completed date.

## Breakdown Record Logic

Each breakdown record captures:

- Breakdown date and time
- Detection method (operator, monitoring, PM inspection, etc.)
- Failure mode (no start, trip, abnormal indication, fire/smoke, etc.)
- Failure cause (electrical, mechanical, environmental, operational)
- Affected production (hours of downtime, units lost)
- Corrective action taken
- Spare parts used
- Labour hours
- Downtime duration

## Root Cause Analysis (RCA) Logic

Each breakdown with significant impact (e.g. > 4 hours downtime, or safety incident, or > $X loss) requires an RCA. The RCA uses a structured method (5 Whys, Fishbone, or FTA) to identify the underlying root cause and the preventive action to avoid recurrence.

## Reliability Metrics

For each asset:

- **MTBF** = total operating time / number of breakdowns
- **MTTR** = total repair time / number of breakdowns
- **Availability** = MTBF / (MTBF + MTTR)
- **Failure rate** = 1 / MTBF

See `procedures/reliability-metrics.md` for the detailed calculation.
