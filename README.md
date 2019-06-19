# Working bumblee be in Ubuntu 18.10 on a Thinkpad X1E

Since I had a lot of trouble getting bumblebee to work on Ubuntu 18.10 on a Thinkpad X1E, I'm sharing the full config so that
other may get it working without having spend hours reading through issues on the bumblebee github.

## System configuration

- **Laptop**: Thinkpad X1 Extreme
- **Model**: 20MFCTO1WW
- **Graphics**:
  - **Integrated**: Intel UHD Graphics 630 (Coffeelake 3x8 GT2)
  - **Discrete**: Nvidia GeForce GTX 1050 Ti Mobile
- **Distro**: Ubuntu 18.10

## Configuration changes

The changes made to the configuration are the following:

- Updated `LibraryPath` and 'XorgModulePath` to correct paths under `driver-nvidia` in `bumblebee.conf`.
- Added screen section in `xorg.conf.nvidia`.

## Prime

Don't use `prime-select` as it interferes with how bumblebee works. When using the 
intel profile it adds `alias nvidia off` in `/lib/modprobe.d/blacklist-nvidia.conf`, preventing 
bumblebee to load the nvidia driver.