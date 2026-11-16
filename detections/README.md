# Detections

- **`sigma/`**: Source of truth, vendor-neutral. Convert to SPL with
  `sigma convert -t splunk -p sysmon detections/sigma/<rule>.yml`.
- **`splunk/`**: SPL searches and IOC lookup CSVs.
- **`wazuh/`**: `local_rules.xml` and CDB lists. Written by hand; Wazuh has no mature official Sigma backend.

Two layers:
1. **IOC matching**: fast, but goes stale quickly (bottom of the Pyramid of Pain).
2. **Behavior (TTP)**: durable; this is where the detection effort goes.

Rule naming: `<attack_id>_<short_description>`, e.g. `t1490_shadow_copy_deletion`.
