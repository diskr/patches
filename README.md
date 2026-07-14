USAGE

git clone https://github.com/diskr/patches -b ksu-next ~/patches

cd $Kernel Dir

Add KernelSU-next

curl -LSs "https://raw.githubusercontent.com/KernelSU-Next/KernelSU-Next/next/kernel/setup.sh" | bash -s legacy

Add CONFIG_KSU=y in device defconfig

Apply patches now

git am ~/patches/0002-add-manual-hooks-for-kernel.patch

git am ~/patches/0001-backport-path_umount.patch

Build kernel now

