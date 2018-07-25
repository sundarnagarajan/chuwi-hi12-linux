### How to report a problem
- Open an issue on github
- You will need a github account

**AT LEAST** provide the following information when you open an issue:
1. Did you use one of the pre-compiled remastered ISOs? If so, which one?
2. If you remastered your own ISO, what was the source ISO (distribution, version, 32-bit or 64-bit)?
3. Did you install on to the main SSD or to an external (USB) medium?
4. While partitioning your target disk during installation, did you create (and use) a **GPT** partition table and an EFI partition?
5. What was the **EXACT** error message you saw, if any, and **at what stage** of install etc
6. Which model of hardware are you using? Sometimes the hardware inside changes, while the model number on the box does not. Provide the following:
    - Link to site where you bought the hardware
    - Output of dmidecode command and dmesg command - most useful
    - Any other information on sticker on the hardware to identify product model, version

### Which distributions and releases are supported
See [distributions.md](/docs/distributions.md)

### I haven't used Linux before - can you help me
See [learning linux](/docs/learning_linux.md)

### I am not familiar with the Linux command line
See [learning linux](/docs/learning_linux.md)

### How can you help beginners who do not know much about computers
See [learning linux](/docs/learning_linux.md)

### I do not understand te instructions for providing the information to report a problem
See [learning linux](/docs/learning_linux.md)

### Why do you use a custom kernel? Why can't you apply your 1-line patch to the upstream Ubuntu Kernel?
This question has been asked so many times, the answer gets [it's own file](/docs/why_custom_kernel.md)!

### With a custom kernel Ubuntu snapd does not work!
It is a compromise. See reason [here]((/docs/why_custom_kernel.md). When Ubuntu sends **all** their apparmor commits upstream, **and** snapd works with upstream stock kernel, this problem (compromise) will go away.
