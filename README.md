# Install Open5GS UPF on Host
This briefly describes the steps for installing [Open5GS](https://github.com/open5gs/open5gs) UPF binary commands.

The specification of the VM that have been confirmed to work is as follows.
| OS | CPU (Min) | Mem (Min) | HDD (Min) |
| --- | --- | --- | --- |
| Ubuntu 24.04 | 1 | 1GB | 10GB |

The network functions of Open5GS for 4G and 5G U-Plane are performed by the following binary commands.

| Generation | Network Function | Binary command |
| --- | --- | --- |
| 4G | SGW-U | open5gs-sgwud |
| | PGW-U | open5gs-upfd |
| 5G | UPF | open5gs-upfd |

---

### [Sample Configurations and Miscellaneous for Mobile Network](https://github.com/s5uishida/sample_config_misc_for_mobile_network)

---

<a id="toc"></a>

## Table of Contents

- [Build Open5GS](#build)
  - [Install required packages for running UPF binary commands on another Host](#install_packages)
  - [How to build only UPF binary commands](#build_only_up)
- [Changelog (summary)](#changelog)

---

<a id="build"></a>

## Build Open5GS

The detailed instructions of building Open5GS can be found as below.

- https://open5gs.org/open5gs/docs/guide/02-building-open5gs-from-sources/

It also explains how to configure and run Open5GS UPF binary commands.

<a id="install_packages"></a>

### Install required packages for running UPF binary commands on another Host

To run the built `open5gs-sgwud` and `open5gs-upfd` on another host, install the following packages on the host.
```
# apt -y install libtalloc-dev libtins-dev libmicrohttpd-dev
```

<a id="build_only_up"></a>

### How to build only UPF binary commands

First for building only UPF binary commands, install the following packages in addition to the above packages.
```
# apt -y install python3-pip python3-setuptools python3-wheel ninja-build build-essential cmake meson libyaml-dev
```
Then apply [this patch](./patches/build_only_up.patch) and build. Only `open5gs-sgwud` and `open5gs-upfd` will be built.

<a id="changelog"></a>

## Changelog (summary)

- [2025.12.07] Added instructions for building only UPF binary commands.
- [2025.11.23] Initial release.
