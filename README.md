# Ft_Linux  >

Read the [PDF](https://linx.zapashcanon.fr/nd44fzbt.pdf)

## Linux From Scratch

The goal is to build a Linux Kernel from scratch and boot from it.

## Init

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
