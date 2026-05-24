# Local Service Audit Toolkit

A small toolkit for maintaining an inventory of local development services and converting authorized Nmap XML output into readable reports.

## Project layout

- `scan_targets/` — Allowed local targets for service inventory.
- `scan_profiles/` — Nmap scan profiles constrained to localhost and loopback targets.
- `sample_data/` — Sample XML outputs used for parser development.
- `reports/` — Generated Markdown and JSON reports.
- `scripts/` — Report conversion and local scan helpers.

## Quick start

```bash
make validate
```
```bash
python3 scripts/nmap_xml_to_markdown.py
```

## Local scan workflow

1. Keep approved targets in `scan_targets/local_targets.txt`.
2. Maintain scan options in `scan_profiles/safe_local.yml`.
3. Store parser fixtures in `sample_data/`.
4. Generate reports into `reports/`.

The included scan helper refuses non-local targets by design.

## Maintenance notes

The helper scan script only accepts localhost or 127.0.0.1 targets.

## Contributing

Keep changes focused, update documentation when behavior changes, and run the validation commands before submitting a pull request.
