# IOC Schema

| Field | Description |
|---|---|
| `type` | `ipv4`, `domain`, `url`, `sha256`, `md5` |
| `value` | Raw (not defanged) indicator |
| `confidence` | 0–100. Multiple independent sources = higher; shared hosting, CDN or Tor = lower |
| `tlp` | Traffic Light Protocol label (`CLEAR` for public sources) |
| `expires` | Retirement date. Defaults: IP +30d, domain/URL +90d, hash none |

Rules: deduplicate on (`type`,`value`); exclude GreyNoise "benign" IPs; never commit malware samples.
