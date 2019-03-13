---
date: 2012-01-18
layout: post
title: "Kernel Upgrade"
category: tech 
tags:
- linux
- gentoo
---

emerge -P gentoo-sources to remove oldest kernel before installing latest
kernel

In most cases, temporary files used during compilation will still remain under
the appropriate source directory under <span style="color:
red;">/usr/src</span>. It is safe to remove these using rm.

You can also safely delete any modules that were used by this kernel. This can
be done by removing the appropriate directories under <span style="color:
red;">/lib/modules/</span> that relate to the kernel versions you are
removing. Be careful not to delete modules belonging to kernels that you still
use!

Finally, you can mount your /boot partition and remove the bzImage
file(s) for the kernel(s) you are pruning. You should also edit your boot
loader configuration so that it no longer references such kernel(s).

emerge -av gentoo-sources to install latest kernel

genkernel --menuconfig --bootloader=grub all

module-rebuild rebuild

check grub for correct syntax

Advanced: Using your old kernel .config to configure a new one It is sometimes
possible to save time by re-using the configuration file from your old kernel
when configuring the new one. Note that this is generally unsafe -- too many
changes between every kernel release for this to be a reliable upgrade
path.

The only situation where this is appropriate is when upgrading from one Gentoo
kernel revision to another. For example, the changes made between
gentoo-sources-2.6.9-r1 and gentoo-sources-2.6.9-r2 will be very small, so it
is usually OK to use the following method. However, it is not appropriate to
use it in the example used throughout this document: upgrading from 2.6.8 to
2.6.9. Too many changes between the official releases, and the method
described below does not display enough context to the user, often resulting
in the user running into problems because they disabled options that they
really did not want to.

Reusing your old config with genkernel

cd /etc/kernels
cp kernel-config-x86-2.6.9-gentoo-r1 kernel-config-x86-2.6.9-gentoo-r2
genkernel all

**KERNEL **

Processor type
Core 2/newer Xeon

To enable Freeview in kernel
Go to:-

 *DEVICE DRIVERS
 *MULTIAMEDIA SUPPORT
 *DVB/ATSC ADAPTERS (NEW)
 *ENABLE SUPPORT FOR VARIOUS USB DVB DEVICES
and select required from list.
