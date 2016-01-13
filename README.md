# patchrepo
Or, when you run a completely unsupported system, you run into issues. Or, you just don't run vanilla.

Everything in here is a patch meant to be applied to code. Some of these might be from distros, but hard to find. Some might be on a bug tracker. Some might be downright custom.

They either fix a bug, fix a build, or change functionality. Point is, I have a lot of them.

I make every effort to slap documentation at the head of every patch, so read it.

* aria2/
    * aria2-1.19.0-leech.patch (works with offsets - 1.19.3)
        * Adds a --disable-seed option. Does what you expect. Now you too can be a leech with a wonderful 0.0 seed ratio (pfft.) This is custom.
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
        * Pale Moon forces internal nss now, so this is of limited utility, but disabling the check with PM allows to build against a patched system-nss.
* wine/
    * wine-1.7.54-force-laa-exec.patch (works - 1.7.55)
        * Environment var 'WINE_FORCE_LARGEADDR' can be set to force a binary to run as if the LAA flag is set. Useful for some games that need dll injection to fix otherwise.
    * wine-1.7.54-mmap-higher-memory.patch (works - 1.7.55)
        * Environment var 'WINE_HIGHER_USERSPACE_MMAP' can be set to do allocation mapping starting at a higher location.
    * wine-1.7.54-opengl-hooking-allow.patch (works - 1.7.55)
        * WINE by default loads glSwapBuffers directly from libGL.so. This makes WINE use RTLD_NEXT so preloads can override glSwapBuffers.
    * All of the above are compatible with staging, too.
* gmpc/
    * gmpc-*-fix-annoyance.patch
        * Disables the annoying dialog when clearing the now playing queue. The average person clears now playing all the time. Seriously a design issue.
