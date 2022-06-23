# obj-m := hello_world.o

# If KERNELRELEASE is defined, we've been invoked from the
# kernel build system and can use its language.
ifneq ($(KERNELRELEASE),)
obj-m := hello_world.o
# Otherwise we were called directly from the command
# line; invoke the kernel build system.
else
# may require `linux-headers-$(uname -r)` or `make headers_install`(https://www.kernel.org/doc/Documentation/kbuild/headers_install.txt)
# KERNELDIR ?= /lib/modules/$(shell uname -r)/build
KERNELDIR ?= ${HOME}/linux
PWD := $(shell pwd)
default:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules
endif