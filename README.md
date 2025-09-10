# IDSA Testbed — UI-Enabled Fork

This repository is a **fork of the IDSA testbed**, adapted to work with the accompanying **UI**.

All functional code originates from the original **IDSA** project. The only additions/changes made in this fork are documented in the following pull request:

- Changes: <https://github.com/LizzieCC/IDS-testbed/pull/1>


## Quick start

### 1) Allow the UI (running on your host) to reach the connectors

Append the following hostnames to your `/etc/hosts` so the UI can resolve the local services:

```bash
sudo sh -c 'echo "127.0.0.1 connectorb connectora omejdn" >> /etc/hosts'
```

> This maps `connectora`, `connectorb`, and `omejdn` to host (`127.0.0.1`), so the UI can access them via ports exposed on your machine.

### 2) Bring everything up with Docker

From the repo root:

```bash
docker compose up
```

This will start the full testbed plus the UI integration defined in the compose file.


## What’s in this fork?

- **Upstream codebase**: All runtime logic and services are from the IDSA testbed.
- **Added/modified bits**: Only what’s necessary to enable the UI integration. See the PR for the exact diff:
  - <https://github.com/LizzieCC/IDS-testbed/pull/1>


## Known limitations

- **UI limit**: UI only accepts small files, tests where made with samples.


## Notes & troubleshooting

- If you already have entries in `/etc/hosts` for these names, avoid duplicates—edit the existing line instead of appending a new one.


## Attribution

This work is based entirely on the **IDSA testbed**. All original authorship and licensing belong to the IDSA project. This fork only adds the minimal UI integration described above.
