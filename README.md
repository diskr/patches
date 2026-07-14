# KernelSU (Backslashxx) Integration Guide

## 1. Clone the required patches

```bash
git clone https://github.com/diskr/patches -b ksu-backslash ~/patches
```

## 2. Change to your kernel source directory

```bash
cd <kernel_source_directory>
```

## 3. Integrate KernelSU (From BackSlashxx github)

```bash
curl -LSs "https://raw.githubusercontent.com/backslashxx/KernelSU/master/kernel/setup.sh" | bash
```

## 4. Enable KernelSU in your kernel configuration

Add the following option to your device's defconfig:

```text
CONFIG_KSU=y
```

## 5. Apply the required patches

```bash
git apply ~/patches/01-exec.patch
git apply ~/patches/02-open.patch
git apply ~/patches/03-stat.patch
git apply ~/patches/04-reboot.patch
git am ~/patches/0001-backport-path_umount.patch
```

## 6. Build the kernel

Rebuild the kernel using your normal build command.
