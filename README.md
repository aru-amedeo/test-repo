# test-repo

Minimal repository used to test [acloud-github-runner](https://github.com/Arubacloud/acloud-github-runner).

Each push to `main` (or a manual dispatch) spins up a fresh Aruba Cloud server,
runs a smoke test, and tears the server down.

---

## Required secrets

Set these in **Settings → Secrets and variables → Actions** before running the workflow:

| Secret | Description |
|--------|-------------|
| `GH_PAT` | Fine-grained PAT with **Administration: Read and write** on this repository |
| `ACLOUD_CLIENT_ID` | Aruba Cloud API client ID |
| `ACLOUD_CLIENT_SECRET` | Aruba Cloud API client secret |

## How to trigger a test run

- **Push to `main`** — triggers automatically
- **Manual** — Actions tab → "Test acloud-github-runner" → Run workflow

## What success looks like

1. `start-runner` completes and outputs a runner label (~2–4 min for server boot)
2. `smoke-test` prints hostname, kernel, CPU, RAM, and disk info from the Aruba Cloud server
3. `stop-runner` deletes the server — verify no leftover in the [Aruba Cloud portal](https://portal.arubacloud.com)
