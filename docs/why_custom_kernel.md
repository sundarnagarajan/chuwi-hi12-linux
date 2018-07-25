This question has been asked too many times, so it gets it's own file!

Why is a [custom kernel needed](https://github.com/sundarnagarajan/rdp-xl200c-linux/blob/master/cherrytrail_kernel_config.md)
The file linked above shows the **minimum** kernel versions required to make various hardware work.
The 1-line patch is required to make bluetooth work on first boot **and** make bluetooth work again after disabling and re-enabling from the GUI.

Possible compromises in using a custom (mainline) kernel rather than upstream (Ubuntu) kernel
- All Ubuntu apparmor patches are not (yet) in mainline
- snapd on Ubuntu checks whether it is an upstream Ubuntu kernel and disallows 'confined mode' if it is not an upstream Ubuntu kernel

Why cant we use (and patch) an upstream Ubuntu kernel

Ubuntu does not have a clear set of steps to apply all Ubuntu patches that are not (yet) upstream to an upstream kernel. This is true for Ubuntu kernels in the standard Ubuntu repositories as well as the kernels in the Ubuntu 'mainline' repository

I tried the following steps from the [Ubuntu wiki Build your own kernel entry](https://wiki.ubuntu.com/Kernel/BuildYourOwnKernel)
```
chmod a+x debian/rules
chmod a+x debian/scripts/*
chmod a+x debian/scripts/misc/*
fakeroot debian/rules clean
fakeroot debian/rules editconfigs # you need to go through each (Y, Exit, Y, Exit..) or get a complaint about config later

fakeroot debian/rules clean
# quicker build:
fakeroot debian/rules binary-headers binary-generic binary-perarch
# if you need linux-tools or lowlatency kernel, run instead:
fakeroot debian/rules binary
```
Only the linux-headers DEB is built!

I also tried retrieving the kernel source for the upstream Ubuntu hwe-16.04-edge kernel using:
```apt-get source linux-image-generic-hwe-16.04-edge```
- ```make bin-deb-pkg``` fails - even with zero changes made!
- ```debian/rules binary``` fails - even with zero changes made!

Policy and goals of this repository
- More important to be able to support all hardware present as compared to running snapd
- More important to be able to track upstream kernels released as compared to running snapd
