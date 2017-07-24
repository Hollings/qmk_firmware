# How to install this firmware on a Planck keyboard using Windows 10

## Enabling Windows Subsystem for Linux on windows 10 Creator update

Make sure you have the 64 bit windows 10 anniversary update.

Search the start menu for *"Use Developer Features"*, and enable developer mode. Wait for the updates to install if any. Reboot the computer if prompted.

Search the start menu for "*Turn windows features on or off*", and enable "Windows Subsystem for Linux".

Search the start menu for "*bash.exe*".  Type "*y*" to accept the terms. If prompted for username and password, use "*root*" and leave password blank

Download and install git if you havent already: https://git-scm.com/download/win

Open a command prompt in the directory you want to install QMK in, and type

    git clone --recurse-submodules https://github.com/qmk/qmk_firmware

Open "Bash on Ubuntu on windows" and navigate to the folder that was just created. Note that windows directories are in the /mnt/ directory. For example:
			

    cd /mnt/c/path/to/qmk_firmware

run:
		

    util/wsl_install.sh

## How to 'make' the firmware for flashing:
Using Bash on Ubuntu still, navigate to the qmk_firmware folder again.

To make the default planck build, run:
			

    make planck-rev4-default

This will make a .hex file in the root directory

## How to flash to the planck
		
Download and install Flip and JRE
			http://www.atmel.com/tools/flip.aspx
			https://java.com/en/download/

Put the planck in boot mode: Hold the reset button on the bottom of the PCB, or press the RESET key (Raise+Lower+Q)

Open FLIP and select ATMEGA32U4 as target device

Select USB as communication medium

open File → Load Hex File  then select the .hex file that was built earlier

Make sure all boxes on the left are checked, and click "Run"

Press "Start Application"

Planck should be up and running now with the new firmware.


# Quantum Mechanical Keyboard Firmware

[![Build Status](https://travis-ci.org/qmk/qmk_firmware.svg?branch=master)](https://travis-ci.org/qmk/qmk_firmware)
[![Gitter](https://img.shields.io/gitter/room/qmk/qmk_firmware.js.svg)](https://gitter.im/qmk/qmk_firmware)
[![Docs Status](https://img.shields.io/badge/docs-ready-orange.svg)](https://docs.qmk.fm)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_firmware.svg?style=social&label=Fork)](https://github.com/qmk/qmk_firmware/)

This is a keyboard firmware based on the [tmk\_keyboard firmware](http://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers, and more specifically, the [OLKB product line](http://olkb.com), the [ErgoDox EZ](http://www.ergodox-ez.com) keyboard, and the [Clueboard product line](http://clueboard.co/).

## Official website

[http://qmk.fm](http://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.

## Supported Keyboards

* [Planck](/keyboards/planck/)
* [Preonic](/keyboards/preonic/)
* [ErgoDox EZ](/keyboards/ergodox/)
* [Clueboard](/keyboards/clueboard/)
* [Cluepad](/keyboards/cluepad/)

The project also includes community support for [lots of other keyboards](/keyboards/).

## Maintainers

QMK is developed and maintained by Jack Humbert of OLKB with contributions from the community, and of course, [Hasu](https://github.com/tmk). The OLKB product firmwares are maintained by [Jack Humbert](https://github.com/jackhumbert), the Ergodox EZ by [Erez Zukerman](https://github.com/ezuk), and the Clueboard by [Zach White](https://github.com/skullydazed).

## Documentation

[https://docs.qmk.fm](https://docs.qmk.fm) is hosted on [Gitbook](https://www.gitbook.com/book/qmk/firmware/details) and [Github](/docs/) (they are synced). You can request changes by making a fork and [pull request](https://github.com/qmk/qmk_firmware/pulls), or by clicking the "suggest an edit" link on any page of the Docs.
