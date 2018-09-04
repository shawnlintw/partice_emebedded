# Install stm32f4 development enviroment on mac osx

<H3> system version : macosx 10.13.6

<H2> Install stlink for stm32 on mac osx

1. brew install libusb libusn-compat
2. brew install pkg-config
3. brew install autoconf automake libtool
4. brew install cmake
4. git clone https://github.com/texane/stlink stlink.git
5. $cd stlink.git
6. $cd cmake
7. $make install
8. [reference](https://www.cnblogs.com/humaoxiao/p/3576732.html)


<H2>Install open-ocd on mac osx

1. [reference](https://gnu-mcu-eclipse.github.io/openocd/install/)


<H2> Install arm gcc tool chain on mac osx

1.  brew tap PX4/homebrew-px4
2.  brew install gcc-arm-none-eabi
3.  [reference](http://wiki.csie.ncku.edu.tw/embedded/freertos)

<H2> Setup and install QEMU enviroment for STM32

1. [reference](https://hackmd.io/s/B19BUj7Ug)

```
>>> mkdir -p workspace
>>> cd workspace
>>> git clone git://github.com/beckus/stm32_p103_demos.git 
>>> git clone git://github.com/beckus/qemu_stm32.git
>>> cd qemu_stm32
>>> git submodule update --init dtc
>>> ./configure --disable-werror --enable-debug \
    --target-list="arm-softmmu" \
    --extra-cflags=-DSTM32_UART_NO_BAUD_DELAY \
    --extra-cflags=-DSTM32_UART_ENABLE_OVERRUN \
    --disable-gtk
>>> make
>>> cd ../stm32_p103_demos
>>> make all
>>> make blink_flash_QEMURUN
```

<H2>FreeRTOS on STM32

1. [reference](https://https://hackmd.io)

```
git clone https://github.com/fbukevin/freertos-basic.git
cd freertos-basic
make
make qemu
```





