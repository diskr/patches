# KernelSU-Next (Legacy) Integration Guide

## 1. Clone the required patches

```bash
git clone https://github.com/diskr/patches -b ksu-next ~/patches
```

## 2. Change to your kernel source directory

```bash
cd <kernel_source_directory>
```

## 3. Integrate KernelSU-Next (Legacy)

```bash
curl -LSs "https://raw.githubusercontent.com/KernelSU-Next/KernelSU-Next/next/kernel/setup.sh" | bash -s legacy
```

## 4. Enable KernelSU in your kernel configuration

Add the following option to your device's defconfig:

```text
CONFIG_KSU=y
```

## 5. Apply the required patches

```bash
git am ~/patches/0002-add-manual-hooks-for-kernel.patch
git am ~/patches/0001-backport-path_umount.patch
```

## 6. Build the kernel

Rebuild the kernel using your normal build command.
