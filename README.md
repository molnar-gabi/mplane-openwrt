# OpenWRT - the mPlane platform

OpenWrt is described as a Linux distribution for embedded devices.
Instead of trying to create a single, static firmware, OpenWrt provides a fully writable filesystem with package management. This frees you from the application selection and configuration provided by the vendor and allows you to customize the device through the use of packages to suit any application. For developer, OpenWrt is the framework to build an application without having to build a complete firmware around it; for users this means the ability for full customization, to use the device in ways never envisioned.

    https://openwrt.org/

## Getting started
Here is a method HowToBuild your own OpenWRT: 

    http://wiki.openwrt.org/doc/howto/build

Check out OpenWRT (it was tested with the release of 38000, you can get it from git as well). Extend your feed, by adding a new line to ``feeds.conf``. Your feed needs to be updated, and the newly downloaded packages must be installed:

    src-git mplane https://github.com/nv-gabor/mplane-openwrt/
    scripts/feeds update -a
    scripts/feeds install -a -p mplane

Now a new ``mPlane`` category most be present in your menuconfig. Below this category all the mplane pckages must be present.

![menuconfig](https://raw.githubusercontent.com/nv-gabor/mplane-openwrt/master/doc/mplane_openwrt.png)

The mPlane directory also contains a submenu, including those ``python3`` modules, whose are currently not supported by OpenWRT but it is needed by the mPlane implementations. These modules are the following:

  - ``python3-tornado``

(``python3-yaml``, ``python3-ssl`` are also needed, but these already the part of the OpenWRT)

## mPlane-specific modules are enumerated below

  - ``mplane-common``: contains generic mPlane modules, whose are widely used by every mPlane instances
  - ``mplane-component``: implementing mPlane components, currently supported technologies:
   - **ping**
   - **OTT**
  - ``mplane-client``: implementing the mPlane client to communicate with the supervisor/component based on the scenario
  - ``mplane-supervisor``: mPlane supervisor module, operating as a central server between the client/component/registry triangle

