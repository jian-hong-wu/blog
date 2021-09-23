## Getting Started With the Accton Open Networking Switches

To install and run Sonic on the Accton switch you will need ONIE and the Sonic binary. Relevant pointers can be found at [Sonic] and [ONIE].

Once installed, please refers to Sonic user guide form configuration and installation.

## ONIE Manual Install

If your Accton Wedge does not have ONIE installed, you will need to install it before you can proceed.

    1. Download the ONIE rescue image from [here]()

    2. Burn the image onto a USB (a USB with a minimum size of 256M is necessary)

    3. Insert the USB into the front USB port on the Wedge

    Attach a serial terminal to the wedge

    Power on the wedge and wait for the BMC to finish booting

    Log into the bmc with the login: root password: 0penBmc

    Attach to the wedge microserver using the command sol.sh

    If the microserver shows the BIOS status screen press F2 to go to the BIOS configuration menu

    In cases where the wedge microserver has already booted into the default linux installation, you will need to either reboot (if possible) or hit ctrl-x, exiting to the BMC and issue the "wedge_power reset" command to power-cycle the microserver, run sol.sh again and hit F2 when the BIOS status screen appears

    One you are in the BIOS configuration, move to the boot screen and change the boot mode from UEFI to Legacy

    In the boot device list, make sure that the USB is set to #1

    Hit esc-0 to or F10 to save and exit the configuration

    The system will now boot from the ONIE rescue USB

    When the ONIE Grub window appears, choose "Embed ONIE"

    ONIE will be installed on the system and the system will automatically reboot
    
    

    IMPORTANT Remove the USB from the system before proceeding to the ONL install

## Sonic Manual Install


