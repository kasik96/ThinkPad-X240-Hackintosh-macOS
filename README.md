# ThinkPad X240 Hackintosh - macOS (High Sierra)
For this tutorial you dont need macOS machine
You can Update moc to Mojave or Catalina after install, dont create USB with it.

Preparation:
- 8GB USB Flash Drive
- Ethernet Connection (no WIFI)
- Linux

1. In terminal (linux) clone this macOS USB creator repo:
```git clone https://github.com/notthebee/macos_usb```

2. Insert USB drive (8GB+) and format it to MS-DOS FAT32

3. Move to repo and start building macOS USB (when asked for version use H - for High Sierra). It will guide you trought the process. When prompted, select formated USB.
```cd macos_usb && bash macos_usb.sh```

4. After USB is created you should have CLOVER/EFI folder mounted, if not, use this command to mount it (? = your USB, for example sdb1)
```sudo mount /dev/? /mnt```

5. Clone this repository 
```git clone https://github.com/kasik96/ThinkPad-X240-Hackintosh-macOS```

6. Move to repo and copy CLOVER files to EFI USB partition
If EFI was mounted automatically:
```cd ThinkPad-X240-Hackintosh-macOS/CLOVER/ && cp -r EFI /run/media/jsdev/CLOVER/```
If EFI was mounted manualy:
```cd ThinkPad-X240-Hackintosh-macOS/CLOVER/ && cp -r EFI /mnt```

7. Boot to USB, select macOS install, and open DISK Utility. In Disk Utility select your internal Disk, and Format it as APFS. 

8. Return to main menu of installation and select Reinstall macOS, select your disc and wait for installation.

9. Your laptop is gonna restart after installation. You need to select macOS USB stick again, and load macOS for internal Hard Drive.

10. Copy this repository to flashdrive and open it in macOS. Download and open MultiBeast from here https://www.tonymacx86.com/resources/multibeast-10-4-0-high-sierra.401/
Select UEFI, and dont change any other settings and click install.

11. After installation, open EFI folder from internal Disk (it should be mounted from MultiBeast) and content of CLOVER folder from this repo to internal Disk EFI Folder. 

12. Install KEXTS from "Post-install KEXTs" with this Guide: https://www.tonymacx86.com/threads/guide-installing-3rd-party-kexts-el-capitan-sierra-high-sierra-mojave-catalina.268964/

13. Remove USB and Restart
