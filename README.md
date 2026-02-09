# xps &nbsp; [![bluebuild build badge](https://github.com/mecattaf/xps/actions/workflows/build.yml/badge.svg)](https://github.com/mecattaf/xps/actions/workflows/build.yml)
## bolt authorization
[from claude]
You have bolt in base.yml (good), and BIOS DMA protection is ON. When you first connect the USB-C cable, boltd will need to authorize the Framework Desktop as a Thunderbolt peer. First connection will require interactive authorization (either via boltctl enroll or a GUI prompt). After that, the device is remembered and auto-authorized on subsequent connections.
You'll want to run boltctl enroll --policy auto <device-uuid> on first setup so future connections are hands-free. This is a one-time thing, not something to bake into the image.

## Installation

To switch an existing Fedora Atomic installation to the latest build:
```
sudo bootc switch ghcr.io/mecattaf/xps:latest
systemctl reboot
```

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/mecattaf/xps
```
