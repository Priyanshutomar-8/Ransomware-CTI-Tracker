# False-Positive Tuning Guide

Baseline window: _24h normal activity on lab VM_ · Last updated: YYYY-MM-DD

| Rule | Known benign triggers | Tuning applied | Alerts before → after |
|---|---|---|---|
| | | | |

## Tuning Principles
- Allowlist by **parent process, signer, or service account**, never hostname alone.
- Drop IOCs for shared hosting, CDN, and Tor exit IPs; check GreyNoise before deploying.
- Every IOC has an `expires` date. Retire stale indicators each release.
- Document every exclusion with a reason and a review date.
