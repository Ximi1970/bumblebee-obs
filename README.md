About Bumblebee
===============

Bumblebee aims to provide support for [nVidia Optimus][optimus] laptops for
GNU/Linux distributions. Using bumblebee-obs, you can use your nVidia card for
rendering graphics which will be displayed using the Intel card.

Note that you cannot disable the Intel GPU even with bumblebee-obs installed.

Support for enabling and disabling the nVidia card is in development. Please
refer to section **Power Management** below.

Bumblebee has been tested on OpenSuSE, Fedora, Mandriva and Ubuntu using the
packages found on the OpenSuSE Build Service (OBS)][obs].

  [obs]:     http://download.opensuse.org/repositories/home:/Bumblebee-Project:
  [optimus]: http://en.wikipedia.org/wiki/Nvidia_Optimus

Installation
------------

### Prerequisites

If you were using an old version of Bumblebee (`<2.3` non-Arch distribution),
please run the `cleanup` script first:

```shell
wget https://raw.github.com/Ximi1970/bumblebee-obs/master/cleanup
chmod +x cleanup
sudo ./cleanup
```

There are several ways to get bumblebee-obs:

### Using your Package Manager (stable, recommended if available)

#### OpenSuSE

1. Installing the nVidia drivers (optional but highly recommended):
    
    Select the nVidia repository for your openSuSE version:

    - **openSuSE 11.3**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/openSUSE_11.3 "Bumblebee nVidia"
        ```

    - **openSuSE 11.4**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/openSUSE_11.4 "Bumblebee nVidia"
        ```

    - **openSuSE 12.1**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/openSUSE_12.1 "Bumblebee nVidia"
        ```

    - **openSuSE Tumbleweed**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/openSUSE_Tumbleweed "Bumblebee nVidia"
        ```

    - **openSuSE Factory**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/openSUSE_Factory "Bumblebee nVidia"
          ```

    Install the nVidia driver packages:

    ```shell
    sudo zypper refresh
    sudo zypper install dkms-nvidia
    sudo zypper install nvidia-compute
    sudo zypper install nvidia-compute-devel
    sudo zypper install x11-video-nvidia
    sudo zypper install x11-video-nvidia-devel
    ```

    For 64bit systems add:

    ```shell
    sudo zypper install nvidia-compute-32bit
    sudo zypper install nvidia-compute-devel-32bit
    sudo zypper install x11-video-nvidia-32bit
    sudo zypper install x11-video-nvidia-devel-32bit
    ```


2. Installing Bumblebee:

    Select the Bumblebee repository for your openSuSE version:

    - **openSuSE 11.3**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/openSUSE_11.3 "Bumblebee"
        ```

    - **openSuSE 11.4**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/openSUSE_11.4 "Bumblebee"
        ```

    - **openSuSE 12.1**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/openSUSE_12.1 "Bumblebee"
        ```

    - **openSuSE Tumbleweed**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/openSUSE_Tumbleweed "Bumblebee"
        ```

    - **openSuSE Factory**:

        ```shell
        sudo zypper ar -f http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/openSUSE_Factory "Bumblebee"
        ```

    Install bumblebee package:

    ```shell
    sudo zypper refresh
    sudo zypper install bumblebee
    ```

    For 64bit systems add:

    ```shell
    sudo zypper install VirtualGL-32bit
    ```

Or you can use Yast to add the repositories and packages.


#### Fedora

1. Installing the nVidia drivers (optional but highly recommended):
    
    Select the nVidia repository for your Fedora version:

    - **Fedora 15**:

        ```shell
        wget http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/Fedora_15/home:Bumblebee-Project:nVidia:latest.repo
        sudo mv -f home:Bumblebee-Project:nVidia:latest.repo /etc/yum.repos.d/
        ```

    - **Fedora 16**:

        ```shell
        wget http://download.opensuse.org/repositories/home:/Bumblebee-Project:/nVidia:/latest/Fedora_16/home:Bumblebee-Project:nVidia:latest.repo
        sudo mv -f home:Bumblebee-Project:nVidia:latest.repo /etc/yum.repos.d/
        ```

    Install the nVidia driver packages:

    ```shell
    sudo yum clean all
    sudo yum install dkms-nvidia
    sudo yum install nvidia-compute
    sudo yum install nvidia-compute-devel
    sudo yum install x11-video-nvidia
    sudo yum install x11-video-nvidia-devel
    ```


2. Installing Bumblebee:

    Select the Bumblebee repository for your Fedora version:

    - **Fedora 15**:

        ```shell
        wget http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/Fedora_15/home:Bumblebee-Project:Bumblebee-unstable.repo
        sudo mv -f home:Bumblebee-Project:Bumblebee-unstable.repo /etc/yum.repos.d/
        ```

    - **Fedora 16**:

        ```shell
        wget http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee/Fedora_16/home:Bumblebee-Project:Bumblebee-unstable.repo
        sudo mv -f home:Bumblebee-Project:Bumblebee-unstable.repo /etc/yum.repos.d/
        ```

    Install bumblebee package:

    ```shell
    sudo yum clean all
    sudo yum install bumblebee
    ```




#### Ubuntu

Needs new install instructions for the OBS install



### Alternative repositories

There are also some alternative repositories:

  - **Bumblebee-unstable**: [Bumblebee-unstable][opensuse-bumblebee-unstable]
        uses the latest cvs/svn/git packages of libturbojpeg and VirtualGL.

  - **Bumblebee-develop**: [Bumblebee-develop][opensuse-bumblebee-develop]
        uses the latest cvs/svn/git packages of libturbojpeg and VirtualGL and
        the opensuse-dev branch.

  [opensuse-bumblebee]:             http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee
  [opensuse-bumblebee-unstable]:    http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee-unstable
  [opensuse-bumblebee-develop]:     http://download.opensuse.org/repositories/home:/Bumblebee-Project:/Bumblebee-develop


### Using the Installation Script

You need to install [VirtualGL][virtgl] `>2.2.1` (`2.2.90` is advised) and
the nVidia driver before you can install Bumblebee.

#### Tarballs (stable)

Tarballs can be found at [Github][tarballs]. Download the file named like
`bumblebee-VERSION.tar.gz`, extract and install it as shown below:

```shell
wget https://github.com/downloads/Ximi1970/bumblebee-obs/bumblebee-VERSION.tar.gz
tar xf bumblebee-VERSION.tar.gz
cd bumblebee-VERSION
sudo ./cleanup
sudo ./install
```

#### Git (stable, branch: master)

```shell
git clone git://github.com/Ximi1970/bumblebee-obs.git
cd bumblebee-obs
sudo ./cleanup
sudo ./install
```

#### Git (unstable, branch: develop)

```shell
git clone git://github.com/Ximi1970/bumblebee-obs.git -b develop --depth 1
cd bumblebee-obs
sudo ./cleanup
sudo ./install
```

**openSuSE** users please use:

```shell
sudo -s <command>
```

  [virtgl]:   http://www.virtualgl.org/
  [tarballs]: https://github.com/Ximi1970/bumblebee-obs/downloads

Usage
-----

After the initial Bumblebee installation, you need to add yourself to the
`bumblebee` group:

#### Ubuntu

```shell
sudo usermod -a -G bumblebee YOUR_USERNAME
```

Replace `YOUR_USERNAME` accordingly and **please double check the command**.
If you accidentally forget the `-a` option, you remove yourself from any
other groups.  

#### openSuSE

```shell
sudo -s usermod -A bumblebee YOUR_USERNAME
```

Replace `YOUR_USERNAME` accordingly.

After adding yourself to the `bumblebee` group, you need to re-login for the
changes to apply.

Applications can be started using Bumblebee by prefixing them with `optirun`.
For example, starting Firefox can be done with:

```shell
optirun glxgears
```

Power Management
----------------

Since version 2.4, we added back-end support for enabling/disabling the card.
Please read [why ACPI was initially removed][acpi-removed], it will help you
understand the current situation about power management. If you understand
what it all means and wish to proceed, here is how to enable it. The package
can be found in the Bumblebee OBS repository:

1. You need to install the `acpi_call` module for your system.

  - **openSuSE**:

        ```shell
        sudo zypper install dkms-acpi_call
        ```

  - **Fedora**:

        ```shell
        sudo yum install dkms-acpi_call
        ```

  - **Ubuntu**: available in the Bumblebee OBS repository:

        ```shell
Needs new instructions
        ```

2. Edit `/etc/bumblebee/bumblebee.conf` and set power management to `Y`.
   You should also set `STOP_SERVICE_ON_EXIT` to `Y`:

    ```
    ENABLE_POWER_MANAGEMENT=Y
    STOP_SERVICE_ON_EXIT=Y
    ```

3. In Bumblebee configuration directory (`/etc/bumblebee`), create two text
   files `cardon` and `cardoff` which should just contain the calls to
   respectively enable and disable the card. Each line should contain a call,
   comments are not allowed.

4. Reboot (or restart Bumblebee daemon) to apply changes.

Check [`bumblebee.conf`][bumblebee-conf] for additional information.

  [acpi-removed]:   https://github.com/Bumblebee-Project/Bumblebee/wiki/ACPI-Removed
  [bumblebee-conf]: https://github.com/Ximi1970/bumblebee-obs/blob/master/install-files/bumblebee.conf

Uninstall
---------

If you used your package manager to install Bumblebee, you can use it to
uninstall it as well (recommended).

Otherwise, you can uninstall Bumblebee by running:

```shell
sudo bumblebee-uninstall
```

Reporting Bugs/Problems
-----------------------

If you have any problem, please read the
[wiki page on reporting issues][wiki-reporting-issues] before submitting a
report.

If a solution to your problem does not exist, create a bug report package
with the `bumblebee-bugreport` tool and
[open an issue on Github][github-issues].

  [wiki-reporting-issues]: https://github.com/Ximi1970/bumblebee-obs/wiki/Reporting-Issues
  [github-issues]:         https://github.com/Ximi1970/bumblebee-obs/issues

Developers
----------

The current bumblebee-obs developer is:

- Ximi1970

Many thanks to the original Bumblebee developers (in alphabetical order):

- ArchangeGabriel
- Lekensteyn
- paulvriens
- Samsagax
- Ximi1970

Various people have also contributed patches and are listed on
[Github][github-contribs].

  [wiki-developers]: https://github.com/Bumblebee-Project/Bumblebee/wiki/Developers
  [github-contribs]: https://github.com/Bumblebee-Project/Bumblebee/contributors

### Useful Links
