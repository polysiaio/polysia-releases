# Polysia releases

Self-hosted, non-custodial USDT (Polygon PoS) payment gateway. This repository contains **only release assets**
(binaries, the deploy bundle, `install.sh`, signed checksums) — no source code.

Website: https://polysia.io · Documentation: https://docs.polysia.io

## Install (Ubuntu 22.04 / 24.04)
```bash
curl -fsSLO https://github.com/polysiaio/polysia-releases/releases/latest/download/install.sh
sudo bash install.sh
```
`install.sh` verifies the Ed25519 signature of `SHA256SUMS` with the Polysia release key embedded in the script and
every SHA-256 before it installs anything.

## Verify a download yourself
```bash
base64 -d SHA256SUMS.sig > SHA256SUMS.sig.bin
openssl pkeyutl -verify -pubin -inkey polysia-release.pem -rawin -in SHA256SUMS -sigfile SHA256SUMS.sig.bin
sha256sum -c --ignore-missing SHA256SUMS
```
`polysia-release.pem` is published on https://docs.polysia.io and embedded in `install.sh`.

Security reports: see https://docs.polysia.io/security
