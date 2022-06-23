- [LDD3, NOTE](#ldd3-note)
  - [CH02](#ch02)
    - [COMPILING AND LOADING](#compiling-and-loading)
      - [MAKE A MODULE](#make-a-module)
      - [MOUNT/UNMOUNT A MODULE](#mountunmount-a-module)


# LDD3, NOTE

- [LINUX KERNEL, doc](https://docs.kernel.org/)

```sh
# reset to 4b0986a Linux 5.18
git reset --hard 4b0986a
```
-

## CH02

- [KBUILD, doc](https://github.com/penLab101/linux/tree/5.18/Documentation/kbuild)

### COMPILING AND LOADING

- install the dependencies [TOOL VERSIONS, doc](https://github.com/penLab101/linux/blob/5.18/Documentation/process/changes.rst)

- [MAKE HELP](https://github.com/penLab101/linux/blob/5.18/Documentation/kbuild/kconfig.rst)

- []

```sh
make menuconfig
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


