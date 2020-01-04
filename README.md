# ThinkPad X240 Hackintosh - macOS Catalina
For this tutorial you DONT need macOS machine, but you need Linux.

Credits:
- https://github.com/Sniki/ALCPlugFix
- https://github.com/Sniki/Lenovo-Thinkpad-X240
- https://github.com/Sniki/OS-X-USB-Inject-All
- https://www.tonymacx86.com/threads/guide-lenovo-thinkpad-x240.245583/
- https://www.reddit.com/r/hackintosh/comments/dfbswz/thinkpad_x240_catalina_success/


What does not work:
- VGA Port
- Card Reader

Preparation:
- 8GB USB Flash Drive
- Ethernet Connection (no WIFI)
- Linux

BIOS Settings:
- Disable Security Chip
- Disable Anti Theft Module
- Disable TPM

1. In terminal (linux) clone this macOS USB creator repo:
```git clone https://github.com/notthebee/macos_usb```

2. Insert USB drive (8GB+) and format it to MS-DOS FAT32

3. Move to repo and start building macOS USB (when asked for version use C - for Catalina). It will guide you trought the process. When prompted, select formated USB.
```cd macos_usb && bash macos_usb.sh```

4. After USB is created you should have CLOVER/EFI folder mounted, if not, use this command to mount it (? = your USB, for example sdb1)
```sudo mount /dev/? /mnt```

5. Clone this repository 
```git clone https://github.com/kasik96/ThinkPad-X240-Hackintosh-macOS```

6. Move to repo and replace EFI USB partition folder with repo EFI folder
If EFI was mounted automatically:
```cd ThinkPad-X240-Hackintosh-macOS/CLOVER/ && cp -r EFI /run/media/jsdev/CLOVER/```
If EFI was mounted manualy:
```cd ThinkPad-X240-Hackintosh-macOS/CLOVER/ && cp -r EFI /mnt```

7. Boot to USB, select macOS install, and open DISK Utility. In Disk Utility select your internal Disk, and Format it as APFS. 

8. Return to main menu of installation and select Reinstall macOS, select your disc and wait for installation.

9. Your laptop is gonna restart after installation. You need to select macOS USB stick again, and load macOS for internal Hard Drive.

10. Download and install Clover to internal HDD from here https://sourceforge.net/projects/cloverefiboot/
Select UEFI options, and dont change any other settings and click install.

11. After installation, open EFI folder from internal Disk (it should be mounted from Clover, you can use Clover Configurator to mount it, if its not) and replace EFI folder on your internal HDD with EFI folder from USB we created. Both should be mounted.

12. Remove USB and Restart

13. Download this repo: https://github.com/Sniki/ALCPlugFix Extract it and open Terminal and navigate to this folder: "ALCPlugFix-master > alc_fix". Run install.sh
```./install.sh```

14. Reboot and everything should work right now.
