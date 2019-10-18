# BootLoader

After booting, the BIOS of the computer reads 512 bytes from the boot devices and, if it detects a two-byte "magic number" at the end of those 512 bytes, loads the data from these 512 bytes as code and runs it.

This kind of code is called a "bootloader" (or "boot sector") and we're writing a tiny bit of assembly code to make a virtual machine run our code and display "Hello world" for the fun of it. Bootloaders are also the very first stage of booting an operating system.

# What happens when your x86 computer starts

You might have wondered what happens when you press the "power" button on your computer. Well, without going into too much detail - after getting the hardware ready and launching the initial BIOS code to read the settings and check the system, the BIOS starts looking at the configured potential boot devices for something to execute.

It does that by reading the first 512 bytes from the boot devices and checks if the last two of these 512 bytes contain a magic number (0x55AA). If that's what these last two bytes are, the BIOS moves the 512 bytes to the memory address 0x7c00 and treats whatever was at the beginning of the 512 bytes as code, the so-called bootloader. In this article we will write such a piece of code, have it print the text "Hello World!" and then go into an infinite loop.
Real bootloaders usually load the actual operating system code into memory, change the CPU into the so-called protected mode and run the actual operating system code.

# Proposal
Writing an x86 "Hello world" bootloader with assembly

Author : Maryam Saeedmehr

Language : assembly The Intel syntax edition


# **Requirements**

For This Project You Need below Requirements :
- nasm : assembler
- qemu : emulator

```shell
$ sudo apt install nasm
$ ‫‪sudo‬‬ ‫‪apt-get‬‬ ‫‪install‬‬ ‫‪qemu‬‬
```

# **Assemble the code**

```shell
$ nasm -o boot.bin boot.asm
```

# **Run It**

```shell
$ qemu-system-x86_64 boot.bin
```


# **Output**


![BootLoader](https://user-images.githubusercontent.com/49061503/67097242-90ff9b80-f1c6-11e9-9105-996d0cf24481.gif)



# **Files**

- <a href="https://github.com/MaryamSaeedmehr/BootLoader/blob/master">`/boot.asm`</a> : This is the Main Assembly File
- <a href="https://github.com/MaryamSaeedmehr/BootLoader/blob/master">`/Markdown`</a> : This is a Report of the project in Persian



# **Support**

Reach out to me at one of the following places!

- Telegram at <a href="https://t.me/BitterOcean" target="_blank">@BitterOcean</a>
- Gmail at <a href="mailto:maryamsaeedmehr@gmail.com" target="_blank">maryamsaeedmehr@gmail.com</a>

