# gentoo-upsys
Gentoo System Upgrade Script

# What does it do?
This script helps you update your Gentoo system.
It will sync the Gentoo Tree, update the Eix database, compile a new kernel (if emerged) and recompile its modules, remove obsolete packages and check the reverse dependencies.

# Dependencies

gentoo-upsys uses `genlop` to parse the emerge log.

If you don't have it installed then:

` # emerge genlop -av `

# Use of external programs

gentoo-upsys supports:
*	eix
*	genkernel (initramfs)
*	grub2 (bootloader configuration)

To use them all, before using gentoo-upsys you need to:

` # emerge eix gentoolkit eix grub -av `

** IMPORTANT **: edit the parameters in gentoo-upsys.conf to your likings before executing it.

# Kernel compiling

gentoo-upsys checks the `/usr/src/linux/` symlink as kernel workspace.
So kernel compiling will work at each emerge "session" **ONLY** if you have the `symlink` USE flag enabled.
## Usage
```
	gentoo-upsys [options]
	---
	Options:
	-n | excludes sync of the gentoo tree
	-e [ebuild] | excludes the specified ebuild
	-q | compiles quietly
	-v | verbose listings (can be used with -q)
```
