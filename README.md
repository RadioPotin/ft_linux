# Ft_Linux  >

Read the [PDF](https://linx.zapashcanon.fr/nd44fzbt.pdf)

## Linux From Scratch

The goal is to build a Linux Kernel from scratch and boot from it.

## Init

We choose [Systemd](https://fr.wikipedia.org/wiki/Systemd) as our prefered init system for our LFS.

Main argument for it is predominant adoption by popular Linux distributions and the all-in-one aspect of it.

### Systemd

#### Origin and controversies

Created by [Lennart Poettering](https://fr.wikipedia.org/wiki/Lennart_Poettering) (author of the [Pid Eins](https://0pointer.net/blog/archives.html) blog) in 2010.

He received **a lot** of backlash by the OS Systems Community because of `systemd`. His detractors reproaching him with going against the UNIX philosophy (KISS, i.e, Keep It Simple, Stupid). It didn't help that `systemd` was progressively and generally accepted as the modern way to initialize a Linux Kernel, demonstrated by the fork of Debian: Devuan, which goal was to keep `Sysvinit` as an initialization method, and be free of `systemd`'s opinionated changes.

`systemd` cut short most practices that were adopted before it. Contrary to `Sysvinit`, its predecessor, `systemd` [increased the coupling with the Linux Kernel](http://0pointer.de/blog/projects/the-biggest-myths.html) which is as much its biggest strength (reliability) and one of its most despised characteristics. 

#### Concepts

Here's a non-exhaustive list of broad but important concepts to understand:

1. Coupling ([wiki](https://en.wikipedia.org/wiki/Coupling_(computer_programming)))
  
2. Kernel APIs 

#### Contents

Systemd offers a lot of binaries of different uses, here are a few important ones:

- /sbin/init ([systemd](https://www.freedesktop.org/software/systemd/man/systemd.html)) for initialization ;
- [journalctl](https://www.freedesktop.org/software/systemd/man/journalctl.html) handles the consulting of the journal ;
- [udev](https://www.freedesktop.org/software/systemd/man/udev.html) handles the discovery of devices and the population of `/dev` ;
- [hostnamectl](https://www.freedesktop.org/software/systemd/man/udev.html) handles the supervision of the machine's hostname ;
- [machinectl](https://www.freedesktop.org/software/systemd/man/machinectl.html) handles  the supervision of the containers launched by systemd ;
- [coredumpctl](https://www.freedesktop.org/software/systemd/man/coredumpctl.html) handles core dumps ;
- [systemd-analyze](https://www.freedesktop.org/software/systemd/man/systemd-analyze.html) handles the inspection of the boot speed ;
- [systemctl](https://www.freedesktop.org/software/systemd/man/systemctl.html) handles services.


## Packages

Some packages from the subject are missing from the LFS-systemd packages list and for good reasons:
- Eudev:
  > Udev is now a virtual package, which can be provided by either Systemd or Eudev.
  >
  > eudev is the Gentoo fork of git://anongit.freedesktop.org/systemd/systemd with the aim of isolating udev from any particular flavor of system initialization. In this case, the isolation is from systemd.
  > From now on, if you choose to manage the device table with udev, you will have to choose between two providers: systemd and eudev.
  > These providers are mutually exclusive:
  >   - if systemd is chosen, the other methods (static, mdev) are not available.
  >   - eudev is not available if systemd is chosen as the init system.
  - [Source](https://patchwork.ozlabs.org/project/buildroot/patch/1378476068-25300-1-git-send-email-eric.le.bihan.dev@free.fr/)
- Sysklogd:
  > systemd has a single monolithic log management program, systemd-journald. This runs as a service managed by systemd. 
  - [Source](https://unix.stackexchange.com/questions/205883/understand-logging-in-linux/294206#294206)
- Sysvinit:
  > Systemd: This package provides an init program and several additional boot and system control capabilities as an alternative to Sysvinit. It is used by many commercial distributions. 
  - [Source](https://linuxfr.org/news/systemd-l-init-martyrise-l-init-bafoue-mais-l-init-libere)
- Time Zone Data:
  >And indeed, {in systemd} timedatectl is managing that file, creating a symbolic link to the appropriate zoneinfo file.
  - [Source](https://serverfault.com/questions/666979/why-do-i-need-to-use-systemd-to-set-my-timezone-in-rhel7)
- Udev-lfs Tarball:
  > All udev sources are merged into the systemd source tree now. All future udev development will happen in the systemd tree. It is still fully supported to use the udev daemon and tools without systemd running, like in initramfs or other init systems. Building udev though, will require the build of the systemd tree, but udev can be properly run without systemd.
  - [Source](https://linuxfr.org/users/sygne/journaux/linux-from-scratch-face-a-udev)

## Ressources

### Required readings before LFS

- [Software Building](https://tldp.org/HOWTO/Software-Building-HOWTO-3.html)
- [Beginners' Guide to Building from Source](http://moi.vonos.net/linux/beginners-installing-from-source/)

### Meat and bones of the project
- [LFS](https://www.linuxfromscratch.org/lfs/view/stable-systemd/index.html)
- [Norm POSIX](https://pubs.opengroup.org/onlinepubs/9699919799/)
- [LSB Specification](https://refspecs.linuxfoundation.org/lsb.shtml)
- [Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html)
- [LSB All Specs](https://refspecs.linuxfoundation.org/LSB_5.0.0/allspecs.shtml)
