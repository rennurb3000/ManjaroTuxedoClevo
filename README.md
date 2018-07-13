- blacklist nouveau 

create /etc/modprobe.d/blacklist-nouveau.conf
#contains 
----
blacklist nouveau
options nouveau modeset=0
---

sudo mkinitcpio -p linuxXY 

#to update initrams where linuxXY is the kernel number ex: linux417

since i have an GTX960M i will have to add the acpi_osi="!Windows 2015"
kernel option

GRUB_CMDLINE_LINUX_DEFAULT = "acpi_osi=\"!Windows 2015\""

#and update grub
sudo grub-mkconfig -o /boot/grub/grub.cfg

