obj-m := pcd.o pcd_lock.o
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
 
