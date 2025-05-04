# Windows 11 Clean Installation Proccess Notes
## Why I Did This
I purchased a used Dell Latitude and wanted a clean and secure start, reinstalling Windows 11 allowed me to:
- Remove all previous data and configurations
- Ensure the system was clean and malware-free
- Take full control over the setup and security
- Learn Installation process hands-on
## Steps
- On a different windows machine, I downloaded Windows 11 Installation Media from Microsoft's official website (https://www.microsoft.com/software-download/windows11).
- Plugged in the usb (used a clean 16gb USB stick).
- Ran the image installer tool and copied the image installer to the USB.
- No Rufus or third-party tools were used.
- Inserted the USB into the target laptop and booted it into BIOS pressing F12.
- Selected boot from USB UEFI and clicked install.
- Selected Custom installation.
- Accessed SSD partitions and deleted all of them except the last unallocated space partition and the USB partition used for installation.
- Chose online installation by connecting to the wifi because it provides the essential security.
- Signed-in using Microsoft account and installed the updates.
- Laptop successfuly booted into windows 11.
- For security reasons Reverted the boot sequence from USB to internal SSD by unchecking the USB option in BIOS.
- Saved changes and rebooted to the freshly installed OS.
- To confirm activation status, I ran the following command in powershell: slmgr /xpr
- After installation Windows 11 was automatically activated (This likely occured due to an embeded OEM key in BIOS).
