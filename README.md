# patchrepo
Or, when you run a completely unsupported system, you run into issues. Or, you just don't run vanilla.

Everything in here is a patch meant to be applied to code. Some of these might be from distros, but hard to find. Some might be on a bug tracker. Some might be downright custom.

They either fix a bug, fix a build, or change functionality. Point is, I have a lot of them.

I make every effort to slap documentation at the head of every patch, so read it.

* aria2/
    * aria2-1.19.0-leech.patch
        * Adds a --disable-seed option. Does what you expect.
        * Also applies on 1.19.1 and 1.19.2 with offset, and works.
* wget/
    * wget-no-egd-libressl.patch
        * Removes reference to egd so libressl is usable.
* libvpx/
    * libvpx-1.4.0_1.3.0backcompat.patch
        * Adds some #defines to enable *some* backcompatibility with libvpx 1.3.0. This is enough to build pale moon against it.
* links/
    * links-no-egd-libressl.patch
        * See the wget patch.
* sdl/
    * sdl-xdata.patch
        * Fixes 'Undefined symbol _XData32' which occurs in some circumstances.
* nss/
    * nss-3.20.1-tls_ecdhe_camellia_gcm.patch
        * Adds ECDHE-Camellia-GCM cipher suites to nss.
* wine/
    * wine-1.7.54-force-laa-exec.patch
        * Environment var 'WINE_FORCE_LARGEADDR' can be set to force a binary to run as if the LAA flag is set. Useful for some games that need dll injection to fix otherwise.
    * wine-1.7.54-mmap-higher-memory.patch
        * Environment var 'WINE_HIGHER_USERSPACE_MMAP' can be set to do allocation mapping starting at a higher location.
