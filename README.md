"Official 4.14.x iterations of Debian kernel packaging for Unstable (Sid) ended with 4.14.17-1.
 Accordingly, there is no Debian kernel packaging for current upstream release Linux 4.14.20.
 Moreover, the currently available Reiser4 patch is for kernel 4.14.1+; thus I had to find a way
 to debianize for stretch-backports (GCC6) the last 'official' kernel packaging if it was to
 successfully wrap around pristine  kernel.org's Linux 4.14.20..."

If you will be using this Debian kernel packaging hack, make sure to first to create a working
 directory, i.e., 
mkdir tlacauhtli

(yes, in Nahuatl ;-)

cd tlacauhtli

git clone https://github.com/Metztli/reiser4-debian-kernel-packaging-4.14.20.git

(you will have a linux directory with linux/debian packaging directory)

With a text editor, (like xvi < https://github.com/martinwguy/xvi > ;-),
 edit linux/debian/changelog by locating the line:

linux (4.14.17-1) unstable; urgency=medium

and remove the number 17 and insert 20, instead, i.e.,

linux (4.14.20-1) unstable; urgency=medium

save your changes and download pristine source 4.14.20: 

wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.14.20.tar.xz

ln -s linux-4.14.20.tar.xz linux_4.14.20.orig.tar.xz

(this last link in 'debian way' is necessary for the packaging routine to proceed)


Added bonus for Linux 4.14.20 ;-)

Likely fixed for Bug#885166: instability with 4.14 regarding KVM virtualization
https://lists.debian.org/debian-kernel/2017/12/msg00374.html

As referenced commit:
https://lists.debian.org/debian-kernel/2018/02/msg00173.html

seems to be already already applied to Linux kernel source tree 4.14.20


Huelmati [Enjoy]!
