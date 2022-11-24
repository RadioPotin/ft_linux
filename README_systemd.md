# [Systemd](https://www.freedesktop.org/wiki/Software/systemd/)

## Origin and controversies

Created by [Lennart Poettering](https://fr.wikipedia.org/wiki/Lennart_Poettering) (author of the [Pid Eins](https://0pointer.net/blog/archives.html) blog) in 2010.

He received **a lot** of backlash by the OS Systems Community because of `systemd`. His detractors reproaching him with going against the UNIX philosophy (KISS, i.e, Keep It Simple, Stupid). It didn't help that `systemd` was progressively and generally accepted as the modern way to initialize a Linux Kernel, demonstrated by the fork of Debian: Devuan, which goal was to keep `Sysvinit` as an initialization method, and be free of `systemd`'s opinionated changes.

`systemd` cut short most practices that were adopted before it. Contrary to `Sysvinit`, its predecessor, `systemd` [increased the coupling with the Linux Kernel](http://0pointer.de/blog/projects/the-biggest-myths.html) which is as much its biggest strength (reliability) and one of its most despised characteristics.

## Concepts

## Contents

Systemd offers a lot of binaries of different uses, here are a few important ones:

- /sbin/init ([systemd](https://www.freedesktop.org/software/systemd/man/systemd.html)) for initialization ;
- [journalctl](https://www.freedesktop.org/software/systemd/man/journalctl.html) handles the consulting of the journal ;
- [udev](https://www.freedesktop.org/software/systemd/man/udev.html) handles the discovery of devices and the population of `/dev` ;
- [hostnamectl](https://www.freedesktop.org/software/systemd/man/udev.html) handles the supervision of the machine's hostname ;
- [machinectl](https://www.freedesktop.org/software/systemd/man/machinectl.html) handles  the supervision of the containers launched by systemd ;
- [coredumpctl](https://www.freedesktop.org/software/systemd/man/coredumpctl.html) handles core dumps ;
- [systemd-analyze](https://www.freedesktop.org/software/systemd/man/systemd-analyze.html) handles the inspection of the boot speed ;
- [systemctl](https://www.freedesktop.org/software/systemd/man/systemctl.html) handles services.

## Ressources

- Lennart_Poettering's blog as a whole but [this](http://0pointer.de/blog/projects/the-biggest-myths.html) in particular.
