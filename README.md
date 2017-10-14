# Realtime-Kernel-RaspberryPi

A compiled kernel image (4.9.34-v7+) and modules for a Raspberry PI (based on Raspbian). It includes Realtime enabled (PREEMPT).

The idea is to bring low latency audio to Raspberry PI.

The [config file](https://github.com/piscue/Realtime-Kernel-RaspberryPi/blob/master/config)

Here is the executed commands, and also the config

```
sudo apt-get install git bc

sudo apt install libncurses5-dev

git clone --depth=1 https://github.com/raspberrypi/linux

cd linux

KERNEL=kernel7

make bcm2709_defconfig

make menuconfig

make -j4 zImage modules dtbs

sudo make modules_install

ls

cp arch/arm/boot/dts/*.dtb ../Downloads/newKernel/boot/

cp arch/arm/boot/dts/overlays/*.dtb ../Downloads/newKernel/boot/overlays/

cp arch/arm/boot/dts/overlays/*.dtb* ../Downloads/newKernel/boot/overlays/

cp arch/arm/boot/dts/overlays/README ../Downloads/newKernel/boot/overlays/

cp arch/arm/boot/zImage ../Downloads/newKernel/boot/$KERNEL.img

sudo cp arch/arm/boot/*.dtb /boot/

sudo cp arch/arm/boot/dts/*.dtb /boot/

sudo cp arch/arm/boot/dts/overlays/*.dtb* /boot/overlays/

sudo cp arch/arm/boot/dts/overlays/README /boot/overlays/

sudo cp arch/arm/boot/zImage /boot/$KERNEL.img

```

Tested on a Raspberry PI 2 and 3
