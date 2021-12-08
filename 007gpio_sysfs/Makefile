obj-m := gpio-sysfs.o
ARCH=arm
CROSS_COMPILE=arm-linux-gnueabihf-
KERN_DIR=~/workspace/ldd/source/linux-5.4
HOST_KERN_DIR=/lib/modules/$(shell uname -r)/build/

all:
	sudo make ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERN_DIR) M=$(PWD) modules
clean:
	sudo make ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERN_DIR) M=$(PWD) clean
help:
	sudo make ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERN_DIR) M=$(PWD) help
host:
	sudo make -C $(HOST_KERN_DIR) M=$(PWD) modules
copy-dtb:
	scp ~/workspace/ldd/source/linux-5.4/arch/arm/boot/dts/am335x-boneblack.dtb  debian@192.168.7.2:/home/debian/drivers
copy-drv:
	scp *.ko debian@192.168.7.2:/home/debian/drivers
