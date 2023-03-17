# Summary Of LPIC-1 5th Edition (2019) -Continued with Linux Professional Institute V-5 (2023)

## 101.1 -Determine and configure hardware settings

Key knowledge areas

- Enable and disable integrated peripherals.
- Differentiate between the various types of mass storage devices.
- Determine hardware resources for devices.
- Tools and utilities to list various hardware information (e.g. lsusb, lspci, etc.).
- Tools and utilities to manipulate USB devices.
- Conceptual understanding of sysfs, udev and dbus.

Partial list of the used files, terms and utilities

- /sys/, /proc/, /dev/, modprobe, lsmod, lspci, lsusb

---

### Device Inspection in Linux

There are two basic ways to identify hardware resources on a Linux system to use specialized commands or to read specific files inside special filesystems.

- `lspci` - Shows all devices currently connected to the PCI bus.
- `lsusb` - Lists USB devices currently connected to the machine.

> every hardware part requires a software component to control the corresponding device. This software component is
> called a kernel module and it can be part of the official Linux kernel (drivers).
> Commands directly related to hardware often require root privileges to execute. The hexadecimal numbers at the beginning of each line are the unique addresses of the corresponding PCI device.

For `lspci` Example:

```shell
$ lspci
00:02.0 VGA compatible controller: Intel Corporation RocketLake-S GT1 [UHD Graphics 750] (rev 04)
...
# option -v displays more detailed output. A specific device can be selected for inspection by providing its ID to the option -d:
# or to ask What command should you execute to identify the kernel module in use for this specific device?
$ lspci -s 00:02.0 -v #or -k
DeviceName: Onboard - Video
Subsystem: ASUSTeK Computer Inc. RocketLake-S GT1 [UHD Graphics 750]
Memory at 4000000000 (64-bit, prefetchable) [size=256M]
Capabilities: <access denied>
Kernel driver in use: i915
Kernel modules: i915
...

$ lspci -s 00:02.0 -k
DeviceName: Onboard - Video
Subsystem: ASUSTeK Computer Inc. RocketLake-S GT1 [UHD Graphics 750]
Kernel driver in use: i915
Kernel modules: i915
```

For `lsusb` Example:

```shell
# With option -t, command lsusb shows the current USB device mappings as a hierarchical tree
$ lsusb -t
Bus 01.Port 1: Dev 1, Class=root_hub, Driver=xhci_hcd/16p, 480M
    |__ Port 2: Dev 2, If 0, Class=Hub, Driver=hub/4p, 480M
        |__ Port 3: Dev 11, If 0, Class=Vendor Specific Class, Driver=mt7601u, 480M

$ lsusb -v -d 1781:0c9f

# gives more detailed data from specific selected port
```

The preferable way to interact with loaded kernel modules is to use the commands provided by the `kmod` package (like insert, remove, list, check properties, resolve dependencies).

Example for `kmod`:

```shell
# kmod [options] command [command_options] | -V, --version - show version
$ kmod list #does same thing as lsmod
Module                  Size  Used by
# Module Module name.  |Size Amount of RAM occupied by the module, in bytes.| Used by Depending modules.
rfcomm                 81920  16
ccm                    20480  6
bnep                   28672  2
...
$ kmod list | grep “kvm” | cat > output1.txt # mostly get used with grep command and get saved by using cat command
```

After testing `kmod` by myself, i have found out it only have ==usage in listing currently loaded modules== and outputting it by `cat` command and thats it.

#### system diagnostics

Command `modprobe` can be used to both load and to unload kernel modules. For unloading a module `modprobe -r` command (as long as they are not being used by a running process). command `modinfo` shows a description, identification, dependencies for the given module. If a module is **causing problems**, the file `/etc/modprobe.d/blacklist.conf` can be used to block the loading of the module. if we want to be more specific on module, the preferred method is to create a separate configuration file, `/etc/modprobe.d/<module_name>`.conf, that will contain settings specific only to the given kernel module.

> The commands lspci, lsusb and lsmod act as front-ends to read hardware information stored by the operating system. This kind of information is kept in special files in the directories `/proc` and `/sys`. The `/proc` directory contains files with information regarding running processes and hardware resources. Some of the important files in /proc for inspecting hardware are:

- `/proc/cpuinfo` - Lists detailed information about the CPU(s) found by the operating system.
- `/proc/interrupts` - A list of numbers of the interrupts per IO device for each CPU.
- `/proc/ioports` - Lists currently registered Input/Output port regions in use.
- `/proc/dma` - Lists the registered DMA (direct memory access) channels in use.

> the `/sys` directory has the specific purpose of storing device information and kernel data related to hardware, whilst `/proc` also contains information about various kernel data structures, including running processes and
> configuration (in RAM).

As new devices are detected, udev searches for a matching rule in the pre-defined rules stored in the directory /`etc/udev/rules.d/`.

#### Storage Devices

In Linux, storage devices are generically referred as block devices, because data is read to and from
these devices in blocks of buffered data with different sizes and positions. Every block device is
identified by a file in the `/dev` directory, with the name of the file depending on the device type (IDE,
SATA, SCSI, etc.) and its partitions.

---

## 101.2 Boot the system

Key knowledge areas

- Provide common commands to the boot loader and options to the kernel at boot time.
- Demonstrate knowledge of the boot sequence from BIOS/UEFI to boot completion.
- Understanding of SysVinit and systemd.
- Awareness of Upstart.
- Check boot events in the log files.

Partial list of the used files, terms and utilities

- dmesg, journalctl, BIOS, UEFI, bootloader, kernel, initramfs, init, SysVinit, systemd.

### The Bootloader

The most popular bootloader for Linux in the x86 architecture is GRUB (Grand Unified Bootloader).
As soon as it is called by the BIOS or by the UEFI, GRUB displays a list of operating systems
available to boot. Sometimes the list does not appear automatically, but it can be invoked by pressing
`Shift` while GRUB is being called by BIOS. In UEFI systems, the `Esc` key should be used instead.

From the GRUB menu it is possible to choose which one of the installed kernels should be loaded
and to pass new parameters to it. like:

- `systemd.unit` - Sets the systemd target to be activated. For example, `systemd.unit=graphical.target`. Systemd also accepts the numerical runlevels as defined for `SysV`. To activate the runlevel 1, for example, it is only necessary to include the number 1 or the letter S (short for “single”) as a kernel parameter.
- `mem` - Sets the amount of available RAM for the system. This parameter is useful for virtual machines so as to limit how much RAM will be available to each guest. Using `mem=512M` will limit to 512 megabytes the amount of available RAM to a particular guest system.
- `maxcpus` - Limits the number of processors (or processor cores) visible to the system in symmetric multiprocessor machines. It is also useful for virtual machines. A value of 0 turns off the support for multi-processor machines and has the same effect as the kernel parameter `nosmp`. The parameter `maxcpus=2` will limit the number of processors available to the operating system to two.
- `quiet` - Hides most boot messages.
- `vga` - Selects a video mode. The parameter `vga=ask` will show a list of the available modes to choose from.
- `root` - Sets the root partition, distinct from the one pre-configured in the bootloader. For example, `root=/dev/sda3`.
- `rootflags` - Mount options for the root filesystem.
- `ro` - Makes the initial mount of the root filesystem read-only.
- `rw` - Allows writing in the root filesystem during initial mount.

> Changing the kernel parameters is not usually required, Kernel parameters must be added to the file `/etc/default/grub` in the line `GRUB_CMDLINE_LINUX` to make them persistent across reboots.
> A new configuration file for the bootloader must be generated every time `/etc/default/grub` changes, which is accomplished by the command `grub-mkconfig -o /boot/grub/grub.cfg`. Once the operating system is running, the kernel parameters used for loading the current session are available for reading in the file `/proc/cmdline`.

### System Initialization

Apart from the kernel, the operating system depends on other components that provide the expected features. Services, also known as **daemons**, may be active all the time as they can be responsible for intrinsic aspects of the operating system.
NOTE - Strictly speaking, the operating system is just the kernel and its components which control the hardware and manages all processes.

The initialization of the operating system starts when the **bootloader loads the kernel into RAM**. **Then, the kernel will take charge** of the CPU and will start to detect and setup the fundamental aspects of the operating system. **The kernel will then open the initramfs (initial RAM filesystem)**. The initramfs is an archive containing a filesystem used as a temporary root filesystem during the boot process. The main purpose of an initramfs file is to provide the required modules so the kernel can access the “real” root filesystem of the operating system. As soon as the root filesystem is available, **the kernel will mount all filesystems configured in /etc/fstab and then will execute the first program, a utility named init.** The init program is responsible for running all initialization scripts and system daemons. There are distinct implementations of such system initiators **apart from the traditional init, like systemd and Upstart**. Once the init program is loaded, the initramfs is removed from RAM.

#### SysV standard

A service manager based on the SysVinit standard controls which daemons and resources will be available by employing the concept of runlevels.

#### systemd

systemd is a modern system and services manager with a compatibility layer for the SysV commands and runlevels. systemd has a concurrent structure, employs sockets and D-Bus for service activation, on-demand daemon execution, process monitoring with cgroups, snapshot support, system session recovery, mount point control and a dependency-based service control.

#### Upstart

Like systemd, Upstart is a substitute to init. The focus of Upstart is to speed up the boot process
by parallelizing the loading process of system services.

### Initialization Inspection

Errors may occur during the boot process, the information collected during the boot process can be useful for tuning and configuration purposes.
The memory space where the kernel stores its messages, including the boot messages, is called the **kernel ring buffer**. boot messages can be output with `dmesg`. In systems based on systemd, command `journalctl` will show the initialization messages with options `-b, --boot, -k or --dmesg`.
Initialization and other messages issued by the operating system are stored in files inside the directory `/var/log/`. the files under /var/log/ can be searched for possible reasons causing the interruption of the boot process.

---

## 101.3 Change runlevels / boot targets and shutdown or reboot system

Key knowledge areas

- Set the default runlevel or boot target.
- Change between runlevels / boot targets including single user mode.
- Shutdown and reboot from the command line.
- Alert users before switching runlevels / boot targets or other major system events.
- Properly terminate processes.
- Awareness of acpid.

Partial list of the used files, terms and utilities

- /etc/inittab, shutdown, init, /etc/init.d/, telinit , systemd, systemctl, /etc/systemd/, /usr/lib/systemd/, wall.

### SysVinit

A service manager based on the SysVinit standard will provide predefined sets of system states, called runlevels, and their corresponding service script files to be executed. being generally assigned to the following purposes:

- Runlevel 0 - System shutdown.
- Runlevel 1 - Single user mode, without network and other non-essential capabilities (maintenance mode).
- Runlevel 2, 3 or 4 - Users can log in by console or network. Runlevels 2 and 4 are not often used.
- Runlevel 5 - It is equivalent to 3, plus the graphical mode login.
- Runlevel 6 - System restart.

a short description of the runlevel’s purpose can also be found in SysV based distributions. The syntax of the `/etc/inittab` file uses this format:

- id:runlevels:action:process

page 40
