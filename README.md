# Flyable VFR days at 96 US flight-training airports (2025)

How many days in 2025 could a student pilot actually fly at each airport? This dataset counts them, airport by airport,
from the hourly METAR record.

- **Full ranking, charts and method:** https://rotatepilot.com/flight-training/flyable-days
- **One page per airport** (month-by-month breakdown), for example
  [Tucson (KTUS)](https://rotatepilot.com/flight-training/flyable-days/ktus),
  [Phoenix Deer Valley (KDVT)](https://rotatepilot.com/flight-training/flyable-days/kdvt),
  [Provo (KPVU)](https://rotatepilot.com/flight-training/flyable-days/kpvu).
  The `page` column of the CSV has the link for every ranked airport.

## Top 10

| Rank | Airport | City | Flyable VFR days | Student-solo days |
|---|---|---|---|---|
| 1 | Tucson International (KTUS) | Tucson, AZ | 365 | 287 |
| 2 | Phoenix-Mesa Gateway (KIWA) | Mesa, AZ | 364 | 325 |
| 3 | Henderson Executive (KHND) | Henderson, NV | 363 | 264 |
| 4 | Phoenix Deer Valley (KDVT) | Phoenix, AZ | 363 | 331 |
| 5 | Chandler Municipal (KCHD) | Chandler, AZ | 363 | 323 |
| 6 | Albuquerque International Sunport (KABQ) | Albuquerque, NM | 360 | 274 |
| 7 | Phoenix Goodyear (KGYR) | Goodyear, AZ | 359 | 323 |
| 8 | Provo Municipal (KPVU) | Provo, UT | 358 | 316 |
| 9 | Ryan Field (KRYN) | Tucson, AZ | 356 | 298 |
| 10 | Salt Lake City International (KSLC) | Salt Lake City, UT | 356 | 253 |

## Files

- `vfr-days-2025.csv` - one row per airport: rank, flyable VFR days, student-solo days, IFR days, and both counts per month.
- `vfr-days-2025.json` - the same data as JSON.

100 airports were processed. 96 are ranked; 4 had an incomplete year of observations and are listed with
`incomplete_year = yes` and no rank.

## Method

Source: routine METAR observations from the
[Iowa Environmental Mesonet ASOS archive](https://mesonet.agron.iastate.edu/request/download.phtml),
January 1 to December 31, 2025. Computed November 2026.

- Window: 08:00 to 16:59 local time, nine hourly slots per day.
- VFR hour: visibility of at least 3 statute miles and a ceiling of at least 1,000 ft.
- Flyable day: at least 6 of the 9 slots have a report and at least 80% of the reported slots are VFR.
- Student-solo day: same day rule with visibility 5 SM, ceiling 3,000 ft, wind 15 kt or less and gusts 20 kt or less.
- IFR day: fewer than 50% of the reported slots are VFR.
- Ranking: flyable days, then percentage of days with data.

## Limits

One year of weather says little about any single year to come. Observations are hourly, so a short squall between
reports is invisible. Legal VFR is not the same as a day a student should fly, which is why student-solo days sit
beside it; neither measures density altitude, runway crosswind, aircraft availability or airspace. This is a weather
record, not a forecast and not a school recommendation.

## License and citation

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Free to use with attribution:

> Rotate Pilot (2026). Flyable VFR days at US flight-training airports, 2025.
> https://rotatepilot.com/flight-training/flyable-days

Corrections: hello@rotatepilot.com
