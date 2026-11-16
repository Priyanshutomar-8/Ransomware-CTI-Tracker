# Ransomware CTI Tracker

Open-source threat intelligence project that tracks a ransomware campaign end to end:
**collection → processing → ATT&CK analysis → intelligence brief → detections (Splunk / Wazuh) → validation → tuning → versioned updates.**

> **Status:** 🚧 In progress. Target campaign: `TBD`

## Intelligence Lifecycle Coverage

| Phase | Artifact |
|---|---|
| Direction | [`intel/requirements.md`](intel/requirements.md) |
| Collection & Processing | [`scripts/`](scripts/), [`iocs/iocs.csv`](iocs/iocs.csv) |
| Analysis | [`intel/attack_layer.json`](intel/) (ATT&CK Navigator) |
| Production | [`intel/brief.md`](intel/brief.md) |
| Detection | [`detections/`](detections/) (Sigma → Splunk SPL, Wazuh XML) |
| Validation | [`validation/test_results.md`](validation/test_results.md) |
| Tuning | [`tuning/false_positive_guide.md`](tuning/false_positive_guide.md) |
| Dissemination | [`CHANGELOG.md`](CHANGELOG.md), GitHub Releases |

## Lab Architecture

```
Wazuh (manager + indexer + dashboard)  ◄── Wazuh agent ──┐
                                                          │
Splunk Enterprise / Free  ◄── Universal Forwarder ────────┤
                                                          │
                                       Windows 10/11 VM + Sysmon
                                       + Atomic Red Team (TTP simulation)
```

## Repository Layout

```
intel/        Intelligence requirements, brief, ATT&CK Navigator layer
iocs/         Normalized, enriched, confidence-scored IOCs (CSV)
scripts/      Collection, enrichment and export automation (Python)
detections/   sigma/ (source of truth), splunk/, wazuh/
validation/   Atomic Red Team test results and screenshots
tuning/       False-positive tuning guide
```

## Sources

CISA #StopRansomware advisories · The DFIR Report · abuse.ch (ThreatFox, MalwareBazaar, URLhaus) ·
AlienVault OTX · MITRE ATT&CK · VirusTotal · AbuseIPDB · GreyNoise Community

## Safety & Handling

- No live malware samples are stored or executed. Only hashes and network indicators.
- Behaviors are simulated with [Atomic Red Team](https://github.com/redcanaryco/atomic-red-team) in an isolated VM.
- IOCs in documents are defanged (`hxxp://`, `1.2.3[.]4`). Raw values live only in `iocs/iocs.csv`.
- All content is **TLP:CLEAR** and derived from public sources.

## Disclaimer

For educational and defensive purposes only. IOCs age quickly; validate before blocking in production.
