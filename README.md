# Install-FreeDOS-on-Raspbian
Install virtual FreeDOS system on a Raspberry Pi Raspbian

1. Install QEMU for emulating i386

apt-get install qemu

2. Build your virtual system with 1024Mb

qemu-img create freedos.img 2014M

3. Download Freedos (FD12CD.iso has to be in the same directory with freedos.img)

http://www.freedos.org/download/download/FD12CD.iso

4. Add each component of the virtual machine

qemu-system-i386 -m 16 -k en-us -rtc base=localtime -soundhw sb16,adlib -device cirrus-vga -hda freedos.img -cdrom FD12CD.iso -boot order=d

5. Install FreeDos 1.2 to harddisk

6. Reboot

7. Change boot order of your virtual system

qemu-system-i386 -m 16 -k en-us -rtc base=localtime -soundhw sb16,adlib -device cirrus-vga -hda freedos.img -cdrom FD12CD.iso -boot order=c​

8. Done!

Create a shortcut for your FreeDOS virtual system (OPTIONAL)
Create a file on your Desktop named FreeDOS.desktop
Edit with text editor, it should contain the following:

[Desktop Entry]
Name=FreeDOS
Icon=/usr/share/pixmaps/gksu-debian.xpm
Exec=sudo qemu-system-i386 -m 16 -k en-us -rtc base=localtime -soundhw sb16,adlib -device cirrus-vga -hda freedos.img -cdrom FD12CD.iso -boot order=c​
Type=Application
Encoding=UTF-8
Terminal=True
Categories=Application;
