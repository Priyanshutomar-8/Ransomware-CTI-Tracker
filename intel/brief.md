# [Group] Ransomware Activity: Intelligence Brief

**Version:** v0.1 · **Date:** YYYY-MM-DD · **TLP:CLEAR** · **Overall confidence:** Low / Moderate / High

## 1. Bottom Line Up Front
_2–3 sentences: who, what, who is targeted, what to do now._

## 2. Key Judgments
- We assess it is **likely** that … (confidence: moderate)
- …
- …

## 3. Initial Access & TTPs

| Tactic | Technique | ID | Observed behavior | Source |
|---|---|---|---|---|
| Initial Access | Exploit Public-Facing Application | T1190 | | |
| Defense Evasion | Impair Defenses: Disable or Modify Tools | T1562.001 | | |
| Credential Access | OS Credential Dumping: LSASS Memory | T1003.001 | | |
| Lateral Movement | Remote Services: RDP | T1021.001 | | |
| Exfiltration | Exfiltration to Cloud Storage | T1567.002 | | |
| Impact | Inhibit System Recovery | T1490 | | |
| Impact | Data Encrypted for Impact | T1486 | | |

## 4. Key Indicators (defanged, high confidence)

| Type | Value | Confidence | Source |
|---|---|---|---|
| | | | |

_Full list: [`iocs/iocs.csv`](../iocs/iocs.csv)_

## 5. Detection Coverage & Gaps

| Technique | Detection | Status |
|---|---|---|
| T1490 | `detections/sigma/…` | ⬜ Planned / ✅ Validated / ❌ Gap |

## 6. Recommended Mitigations (prioritized)
1. …
2. …
3. …

## 7. Sources

| # | Source | Reliability |
|---|---|---|
| 1 | | A–F |
