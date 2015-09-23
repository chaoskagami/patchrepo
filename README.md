# patchrepo
Or, when you run a completely unsupported system, you run into issues. Or, you just don't run vanilla.

Everything in here is a patch meant to be applied to code. Some of these might be from distros, but hard to find. Some might be on a bug tracker. Some might be downright custom.

They either fix a bug, fix a build, or change functionality. Point is, I have a lot of them.

* aria2/
    * aria2-1.19.0-leech.patch
        * Adds a --disable-seed option. Does what you expect.
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
