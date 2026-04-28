# test-repo

Minimal repository used to test [acloud-github-runner](https://github.com/Arubacloud/acloud-github-runner).

Each push to `main` (or a manual dispatch) spins up a fresh Aruba Cloud server,
runs a smoke test, and tears the server down.
