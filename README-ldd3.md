- [LDD3, NOTE](#ldd3-note)
  - [CH02](#ch02)
    - [COMPILING AND LOADING](#compiling-and-loading)
      - [MAKE A MODULE](#make-a-module)
      - [MOUNT/UNMOUNT A MODULE](#mountunmount-a-module)
    - [IDE \&\& CLANGD SETUP](#ide--clangd-setup)


# LDD3, NOTE

- [LINUX KERNEL, doc](https://docs.kernel.org/)

```sh
# reset to 4b0986a Linux 5.18
git reset --hard 4b0986a
```

## CH02

- [KBUILD, doc](https://github.com/penLab101/linux/tree/5.18/Documentation/kbuild)


### COMPILING AND LOADING

- install the dependencies [TOOL VERSIONS, doc](https://github.com/penLab101/linux/blob/5.18/Documentation/process/changes.rst)

- [MAKE HELP](https://github.com/penLab101/linux/blob/5.18/Documentation/kbuild/kconfig.rst)

```sh
# use the config of the current kernel
cp /boot/config-$(uname-r) .config
make menuconfig
make -j$(nproc)
make modules
make modules_install # e.g. to /lib/modules/$(uname -r)
make install
# or if need manually adjustment
# sudo update-initramfs -c -k 5.18.0
# sudo upgrade-grub
```

#### MAKE A MODULE

- [BUILD AN ERTERNAL MODULES, doc](https://github.com/penLab101/linux/blob/5.18/Documentation/kbuild/modules.rst)

- Makefile

```Makefile
obj-m := hello_world.o
# module-objs := file1.o file2.o # for multiple files
```

```sh
# Building an external module, generate `hello_world.ko` file
make -C $HOME/linux M=$PWD
```

#### MOUNT/UNMOUNT A MODULE

```sh
modprobe
insmod
rmmod
```

### IDE && CLANGD SETUP

- [CLANGD, doc](https://clangd.llvm.org/installation)

```compile_flags
-I/path/to/linux/include
-I/path/to/linux/arch/<arch>/include
```

