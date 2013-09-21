STM32-discovery
===============

Code for STM32 Discovery boards, including makefiles, to be used with a linux machine.

Toolchain: gcc-arm-none-eabi
Download toolchanin

wget https://launchpad.net/gcc-arm-embedded/4.7/4.7-2013-q2-update/+download/gcc-arm-none-eabi-4_7-2013q2-20130614-linux.tar.bz2

tar -xvf gcc-arm-none-eabi-4_7-2013q2-20130614-linux.tar.bz2

cd gcc-arm-none-eabi-4_7-2013q2

mv gcc-arm-none-eabi-4_7-2013q2 /usr/local/gcc-arm-none-eabi



For flashing and loading of images use stlink2.

git clone https://github.com/texane/stlink.git

cd stlink

make 

make install


To load image:

st-util

This will start a gdb server at port 4242.


Then load image using arm-none-eabi-gdb

arm-none-eabi-gdb  image_file.elf

target extended-remote :4242

load

tbreak main

c



