# patch-mst-debian-jessie-3.16.0-4-amd64
This is the patch to get DisplayPort 1.2 MST working with the debian jessie kernel 3.16.0-4-amd64

First of all thanks to :
- Dave Airlie (http://cgit.freedesktop.org/~airlied/linux/log/?h=drm-i915-mst-v3.16) for the patch
- Jouke Waleson (https://tech.mendix.com/linux/2014/09/06/debian-testing-kernel-3.16-displayport-mst/) for the instructions

You just have to download this patch and follow instructions provided by Jouke on his post. (section *Getting the kernel source and applying the patch*)

On my side patching the kernel allowed me to properly use the Dell docking station (and connect my 2 monitors and have 2 separate displays) with my Dell Latitude E7450.

Note :

I had to run this command as well (see https://wiki.debian.org/HowToRebuildAnOfficialDebianKernelPackage) to properly rebuild linux-headers-XXX-common package

fakeroot make -f debian/rules.gen binary-arch_amd64_none_real

Then I installed the new patched kernel using :

dpkg -i linux-headers-3.16.0-4+mst.1-amd64_3.16.7-ckt11-1+deb8u3+mst.11_amd64.deb linux-headers-3.16.0-4+mst.1-common_3.16.7-ckt11-1+deb8u3+mst.11_amd64.deb linux-image-3.16.0-4+mst.1-amd64_3.16.7-ckt11-1+deb8u3+mst.11_amd64.deb
