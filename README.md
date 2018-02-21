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

git clone https://github.com/Metztli/reiser4-debian-kernel-packaging-4.14.20.git linux

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

since referenced commit:
https://lists.debian.org/debian-kernel/2018/02/msg00173.html

seems to be already applied to Linux kernel source tree 4.14.20

P.S. YES! Bug#885166 has been fixed in 4.14.20!

...
"If I used git correctly, then 4.14.20 already has
2a266f23550be997d783f27e704b9b40c4010292, so I tried 4.14.19. 4.14.19 on
the one virt host that had the most violent failures failed in the first
hour of operation, but with a slightly different error behavior that I
was used to. I am therefore not sure whether we are not talking about
multiple issues, one of them having been fixed somewhere in between
4.14.13 and 4.14.19."
...

https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=885166

Huelmati [Enjoy]!
