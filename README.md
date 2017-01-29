# DM1000-audio-cards
This repository contains Firmware, docs, Windows and Mac drivers for DM1000-based audio cards, such as

* [Terratec Aureon 7.1 FireWire](#terratec-aureon-71-firewire)
* M-Audio Audiophile sound cards

#Terratec Aureon 7.1 FireWire

![Terratec Aureon 7.1 FireWire](https://github.com/romansavrulin/DM1000-audio-cards/raw/master/Aureon/Images/Aureon7.1FireWire_Side_s.jpg)

#Resolving boot or invalid firmware issue of soundcard
If your card lights all LEDs and doesn't respond to any button, Firewire link connection or any other actions, you should check what's going on with system firmware inside your card. Just connect UART to the following header inside and open your favorite terminal with `11520 8n1` speed settings.

If you see that firmware image is invalid, you need to upload [this one](https://github.com/romansavrulin/DM1000-audio-cards/raw/master/Aureon/AureonFW/Aureon%20v3.2.13.31.bcd) via `XModem` protocol, selecting appropriate option in the bootloader menu.

```
Bootloader: CRC ok! Id=00000001, V=00002809, 20040719-074807UT
Debugger:   invalid
Image:      invalid
CnE:        CRC ok! Id=00000002, V=03020d1f, 20041105-165722UT
```

!!!Important!!! Also check the autostart option of bootloader, it should be set to `0 = application`

![UART header pinout](https://github.com/romansavrulin/DM1000-audio-cards/raw/master/Aureon/IMG_4794.jpg)

#Running Aureon control app on Mac

* Install [Latest available Mac software](https://github.com/romansavrulin/DM1000-audio-cards/raw/master/Aureon/Software/Aureon7.1FireWire_App_MAC_OS_X_1.10.dmg)
* It will ask you to reboot
* Try running `AureonFwCpl` from your app folder
* If you get an error dialog containing `could not find server.  You need to start one on this machine first` just run `sudo PhaseXXService` on a terminal. Not sure how to make it autostart. If someone can do it - make a pull request with a readme corrected.
