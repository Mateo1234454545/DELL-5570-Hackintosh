Hackintosh on Dell 5570


       OPENCORE UPDATE 4/7/21

	•	Summer Update
	•	Compatible with MacOs Monterey.



Working hard to keep this project running. If you like it and want to contribute :

DONATE

BTC : 1EPgnnSDinaJmXqgEsLERgbQQk8uZhoQks

ETH : 0x0914a29ffffa4a65d5b15bdb3f57c66b607c35e5  (ERC20)

VET : 0x0914a29ffffa4a65d5b15bdb3f57c66b607c35e5

DOGE : D9ygFekkE295XYSgoosUhybuZZsYwVSwKd




CHANGES:

1) Injected new applealc.kext ,modified by me. Now sound from headphones and mic are working even after waking from sleep and with no need of ssdt and codeccommander.kext !!!!
Only bug is that right after boot ,sound from headphone doesn't work. Put your laptop to sleep and after that sound is always there.
Working to find a solution for this bug , too.

2) Solve bluetooth disapearring on Monterey.

3) Remove mem2 device.

4) Use patched voodoops2controller.kext  from Rehabman. Solves caps lock light staying on.

5) Restore smbios to macbookpro 15,2. If you want to keep 16,3 go ahead , not much diffirence anyway.

6) Update to most recent opencore /kexts /drivers versions.


Specs :

Cpu : Intel i5-8250u at 1.6ghz (Kabylake-r)
Gpu : Intel UHD620
Ram : 8gb ddr4 2400ghz
Hard disk : I replaced the standard hd with a Samsung 860 evo and I added a Samsung 860evo at m2 slot. 
Wifi/bt : Factory qualcomm won't work. I replaced it with a Broadcomm 94360CS2 working natively. Fingerprint sensor : Won't work with mac, so I disabled it. 
Card reader : I don't need it , so I disabled it from bios.

What is working : Pretty much everything...

CPU management : native cpu management 
Battery managment : getting 4,5-5 hours , with browsing , music and office editing. Better that windows 10 !!! 
Audio : working great including headphones. 
Sleep/wake : lid close / open working as it should.
Precision touchpad : working close to a real mac , with almost all gestures.
Brighness / volume control : fn + F1,F2,F3,F4 for volume , fn+F11,F12 for display brighness. 
Camera : ok

What we need : I will not get into details. You can read the great guides at forum for getting a usb installer.

Some notes :

	✓	Dispaly analysis is set to 1920x1080 (default). If you find (like me) that fonts are too small you can use a scaled one (like 1600x900). Or you can run one-key-hidpi-master to get HDIPI , too.

	✓	You have to implement proper usb management, following this guide :guide-creating-a-custom-ssdt-for-usbinjectall-kext.211311. This is very importart!!! I've already placed a ssdt for usb , but be sure to check if it is working ok for your system , too. As I said I've disabled card reader and fingerprint sensor , as they don't work on hackintosh.

	✓	Uncheck smart zoom at preferences/trackpad.

	✓	Get yourself a serial number in config.plist/smbios.

	✓	There is a Bios editing section at the end of this section. If you don't follow it you won't ne able to boot with the current OC folder.



                                                     


GUIDE FOR BIOS EDITING

To get a fully optimise Macos you should change some setting in BIOS. This is very dangerous and could lead to a bricked laptop. Use it at your own risk. You have been warned !!!!

If you still want to try then :

Follow this guide : http://forum.notebookreview.com/threads/tutorial-xps-15-9550-9550-bios-advanced-options.810307/

and change these settings:

DVMV PRE-ALLOCATED set to 64MB: setup_var 0x795 0x2

DVMT TOTAL GFX MEM set to MAX: setup_var 0x796 0x3

CFG Lock
set to Disabled: setup_var 0x4ED 0x0

I2CO INTERUPT MODE set to GPIO Interrupt : setup_var 0x272 0x0




CREDITS

Thanks to stevezhengshiqi for guide of Xiaomi-Pro.

Thanks to vit9696/Acidanthera for providing AppleALC, Lilu, VirtualSMC, and WhateverGreen.

Thanks to alexandred and hieplpvip for VoodooI2C.

Especially , Thanks to RehabMan for guiding me all the way. Without his help this guide wouldn't be possible.

	✓	Get yourself a serial number in config.plist/smbios.

	✓	There is a Bios editing section at the end of this section. If you don't follow it you won't ne able to boot with the current OC folder.

OpenCore Update 5/19/21

•	Update OC and kexts to latest version 0.6.9

•	Added/Removed some ACPI patches for optimization

•	Testing branch has been opened to add a new AppleALC version that doesn't require CodecCommander to work. If you intend to test the changes, please make sure to uninstall CodecCommander from /L/E or /S/L/E beforehand

•	More in-depth notes of the changes [here](https://docs.google.com/document/d/1ZCY6Fcx41PItnm4POoBZlHppS6xRBjGxTa2FRvrmpsc)

OpenCore Update 1/1/21

•	Update OC and kexts to latest version 0.6.4

•	Update smbios to 16,3

•	Replaced ACPI patch BRT6 with BrightnessKeys.kext

•	More SSDT and Config.plist optimization


BIG SUR UPDATE  14/8/20

•	Update OC and kexts to latest version  (see note 1)

•	Revert back to smbios 15,2.

•	SSDT's and config.plist optimisation.

•	Solved audio from headphones disappearing after sleep , with SSDT-HRT.aml. Needs more testimg    
       though.

note 1 : I use an older version of whatevergreen.kext , whick works on Big Sur but doesn't have the issue where aster waking from sleep gpu hangs at max frequency.



GUIDE FOR BIOS EDITING

To get a fully optimise Macos you should change some setting in BIOS. This is very dangerous and could lead to a bricked laptop. Use it at your own risk. You have been warned !!!!

If you still want to try then :

Follow this guide : http://forum.notebookreview.com/threads/tutorial-xps-15-9550-9550-bios-advanced-options.810307/

and change these settings:

DVMV PRE-ALLOCATED set to 64MB: setup_var 0x795 0x2

DVMT TOTAL GFX MEM set to MAX: setup_var 0x796 0x3

CFG Lock
set to Disabled: setup_var 0x4ED 0x0

I2CO INTERUPT MODE set to GPIO Interrupt : setup_var 0x272 0x0


Working hard to keep this project alive and up to date. If you feel like it you can buy me a beer : https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=AUQFM3DPPEEEC&source=url



CREDITS

Thanks to stevezhengshiqi for guide of Xiaomi-Pro.

Thanks to vit9696/Acidanthera for providing AppleALC, Lilu, VirtualSMC, and WhateverGreen.

Thanks to alexandred and hieplpvip for VoodooI2C.

Especially , Thanks to RehabMan for guiding me all the way. Without his help this guide wouldn't be possible.
