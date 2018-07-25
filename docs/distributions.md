## For now, **only** Ubuntu is supported.

If the solution involves remastering the standard Ubuntu ISO, the following Ubuntu distributions should be supported:
- 'Standard' Ubuntu (Unity or gnome as the case may be)
- xubuntu
- Ubuntu Mate - primarily because I use it, but many 'novice' users seem to like it too

The following releases of Ubuntu are expected to be supported:
- The latest release (LTS or otherwise)
- The last LTS release, that is **different** from the latest release that is still supported by the upstream distribution (Canonical / xubuntu / Ubuntu Mate community)

## What about kubuntu, Linux Mint, Elementary OS ... etc
Remastering the ISO and testing takes a while. The remastering script **should** work on other Ubuntu derivatives. 

Give it a spin and open an issue, indicating whether it worked, and what if anything did **not** work. I will include it under list of tested distributions.

## What about Debian
Many things that we fix should **just work** under Debian too.
That said, if we use a custom kernel (and maybe a custom kernel PPA), getting that to work in Debian may involve additional work.
The names of files inside the ISO in a Debian ISO may also be different. Take a look at [```ubuntu_remaster_iso.sh```](https://github.com/sundarnagarajan/bootutils/blob/master/scripts/ubuntu_remaster_iso.sh) on my [bootutils repository](https://github.com/sundarnagarajan/bootutils) and send me a pull request if you can make changes to this file to make it work successfully on Debian.

## What about other distributions - like Arch, Gentoo, Fedora, Centos, Red Hat, Suse, Slackware
- First of all, **ONLY distributions supporting a Live ISO** will ever be supported
- Need help in understanding the ISO structure of the particular distribution. Take a look at [```linusiso.py```](https://github.com/sundarnagarajan/bootutils/blob/master/scripts/linuxiso.py) on my [bootutils repository](https://github.com/sundarnagarajan/bootutils). Send a pull request if you manage to make the various methods work correctly on the distribution of your choice.
- Need help in figuring out how to compile packages of upstream stock kernels for your distribution and installing them. If you have clear instructions, I can incorporate them into my [```kernel_build``` repository](https://github.com/sundarnagarajan/kernel_build)
- Need help in figuring out how to identify the packages required based on commands that we need in your chosen distribution
- Need help (links) to command line installation / removal of packages in your chosen distribution
- If your chosen distribution does **not** use systemd, need pointer to which init your chosen distribution uses

Overall, the goal of this repository is around:
- Exploring what works and doesn't work in Linuc on a specific type of hardware (usually but not necessarily based on Intel Cherry Trail)
- Finding fixes to make everything work in Linux (usually kernel drivers, firmware and maybe some user-space tools / commands)
- Incorporating all solutions into a **live-bootable ISO, so that **everything just works** in the live session. I cannot over-emphasize how important this goal is.
- Support installing from the live-bootable ISO, and have everything **just work** on the installed version also.

Given the most important goals above, it seems reasonable to focus on Ubuntu for now. Once everything works (in the live-bootabls ISO), advanced users could possibly explore and retrofit the changes / fixes in their chosen distribution themselves.

