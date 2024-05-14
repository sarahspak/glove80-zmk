# MoErgo Glove80 Custom Configuration for ZMK

![MoErgo Logo](moergo_logo.png)

This repo is the official ZMK configuration of the MoErgo Glove80 wireless split contoured keyboard. Use it to develop your own keymap and easily build your own ZMK firmware to run on your Glove80.

**NOTE: You can also customize the layout of your Glove80 keyboard with the Glove80 Layout Editor webapp. For most users Glove80 Layout Editor is the recommended and simpler option. More information is available at the official MoErgo Glove80 Support site (see resources below).**

These steps will get you using your keymap on your keyboard in the fastest time possible. It uses the GitHub Actions feature to build your firmware online.

If you are looking to dig deeper into ZMK and develop new functionality, it is recommended to follow the steps of installing ZMK as found on the official ZMK documentation site (linked below).

## Resources

- The [official MoErgo Glove80 Support](https://moergo.com/glove80-support) web site. Glove80 documentation and other technical resources.
- The [official MoErgo Discord Server](https://moergo.com/discord). Instant conversations with other Glove80 users.

- The [official ZMK Documentation](https://zmk.dev/docs) web site. Find the answers to many of your questions about ZMK Firmware.
- The [official ZMK Discord Server](https://discord.gg/8cfMkQksSB). Instant conversations with other ZMK developers and users. Great technical resource!

- The [official Glove80 ZMK Distribution](https://github.com/moergo-sc/zmk). Repositiory for ZMK firmware customized for Glove80.

## Instructions

1. Log into, or sign up for, your personal GitHub account.
2. Create your own repository using this repository as a template ([instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)) and check it out on your local computer.
3. Edit the keymap file(s) to suit your needs
4. Commit and push your changes to your personal repo. Upon pushing it, GitHub Actions will start building a new version of your firmware with the updated keymap.

## Firmware Files

To locate your firmware files and reflash your Glove80...

1. log into GitHub and navigate to your personal config repository you just uploaded your keymap changes to.
2. Click "Actions" in the main navigation, and in the left navigation click the "Build" link.
3. Select the desired workflow run in the centre area of the page (based on date and time of the build you wish to use). You can also start a new build from this page by clicking the "Run workflow" button.
4. After clicking the desired workflow run, you should be presented with a section at the bottom of the page called "Artifacts". This section contains the results of your build, in a file called "glove80.uf2"
5. Download the glove80.uf2
6. Flash the firmware to Glove80 according to the user documentation on the official Glove80 Glove80 Support website (linked above)

Your keyboard is now ready to use.

# how to flash the firmware

The steps to load the new firmware are:

1. first plug in the USB-C cable to the right half of your Glove80 and to the host computer.
2. Put the right half into bootloader mode. On the default key layout, this is done by pressing the keys Magic + '(note: single-quote). If this doesn’t work or if you have changed your layout, please see the section on Putting Glove80 into Bootloader for Firmware Loading.
3. If successful, the bootloader will present a USB Mass Storage Device. As an example, on Windows you will see a File Explorer window with the name GLV80RHBOOT.

4. Copy the .UF2 file onto this Mass Storage Device. If successful the Mass Storage Device will disappear.
5. Next plug in the USB-C cable to the left half of your Glove80 and to the host computer.
6. Put the left half into bootloader mode. On the default key layout, this is done by pressing the keys Magic + Esc (Tab on the current layout). If this doesn’t work or if you have changed your layout, please see the section on Putting Glove80 into Bootloader for Firmware Loading.
7. If successful, the bootloader will present a USB Mass Storage Device. As an example, on Windows you will see a File Explorer window with the name GLV80LHBOOT
8. Copy the .UF2 file into this Mass Storage Device. If successful the Mass Storage Device will disappear.
9. After a firmware version change or changes made to Advanced Configuration, it is generally recommended to perform a Configuration factory reset and re-pairing left and right halves procedure.

# How to perform a configuration factory reset

Since the pairing information between the left half and the right half is also stored in the non-volatile configuration in both halves, if you perform a configuration factory procedure on one half, you must also perform a configuration factory reset on the other half. Left and right halves will automatically re-pair with each other, after the configuration factory reset.

To perform the configuration factory reset procedure on the left half:

    Switch off the power switch of both halves of Glove80
    Referring to the row-column key above, hold C6R6 + C3R2 (Magic + 3 on the default layout) on the left half
    While holding the two keys, switch on the power switch of the left half
    Wait for 5 seconds while holding the two keys
    Switch off the power switch of the left half

To perform the configuration factory reset procedure on the right half:

    Switch off the power switch of both halves of Glove80
    Referring to the row-column key above, hold C6R6 + C3R2 (PgDn + 8 on the default layout) on the right half
    While holding the two keys, switch on the power switch of the right half
    Wait for 5 seconds while holding the two keys
    Switch off the power switch of the right half

To re-pair the left half and the right half:

    Switch on the power switch of the left half and the right half at the same time
    Enable RGB (Magic + t on the default layout) and check that both halves have RGB turned on (unless your Glove80 is a Kickstarter “Standard Edition” with no RGBs on the right hand). If the RGBs are not turning on a particular half, connect the half to a power source via USB and try again.
    Disable RGB (Magic + t on the default layout)
    Wait for at least one minute for the new configuration to be persisted into the memory.
