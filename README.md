# klibc-kinit-standalone

This is the kinit code (and related utilities) extracted from the `klibc`
project (https://git.kernel.org/pub/scm/libs/klibc/klibc.git) and made to
build/work without klibc itself. The primary purpose of this is to be used
in initramfs environments, without actually using the other klibc userland.

In Chimera, this is to be used together with `bsdutils`, which already
provides a reasonably small core userland, but not the `kinit` utilities.

The `klibc` project itself is provided under the terms of the MIT license.
However, certain kernel headers are also shipped, which are licensed under
the GPLv2.

## Building

This fork uses `meson`. Therefore, you will need that installed. You will
also need the Linux kernel headers installed.

Quick instructions:

```
$ mkdir build
$ cd build
$ meson .. --prefix=/usr
$ ninja all
$ ninja install
```
