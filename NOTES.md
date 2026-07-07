# Notes

## Fix explained

The double-booking bug was in the overlap check. The original logic only detected certain overlap directions and missed bookings that began before an existing booking but extended into it. The new comparison detects inclusive overlap from either direction, so any shared rental date is blocked.

## Original failure example

2026-01-08 to 2026-01-12 was wrongly allowed by the original code even though it overlaps the Canon DSLR booking from 2026-01-10 to 2026-01-15.

## AI use

AI was used to review the existing logic, identify edge cases, and help plan the fixes. I checked the output by reading the repository's business rules, reviewing every code change, running focused backend checks, manually testing overlapping and non-overlapping dates, checking same-day and multi-day pricing, confirming maintenance equipment could not be listed or booked, and testing the frontend date update behavior.
