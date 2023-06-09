# Black Iron Project #
<img src="https://imgur.com/rUip0he.jpg">

A Small Description of the Iron V3 (V1 is IRON Los & V2 IronOS Project)
----------------------------------

This ROM is a based on Pixel Experience for this Android Version (A13), so it will follow all its developments.
I just added the features that I think are useful for my use of the device.
In this case it is very similar to the other rom that I follow with many of my friends which is the PEX (Pixel Extended), by Aryan Gupta
I just added something extra and to have fun in my spare time
Since I worked on it, I thought I'd share the work with those who make the same use of the device as me !!
Good building.

Credits
-------
- CyanogenMod/LineageOS
- Derpfest
- AICP
- AOSiP
- AOSPA
- BootleggersROM
- CrDroid
- DirtyUnicorns
- NitrogenOS
- OmniROM
- PixelExperience
- Pixel Extended
- POSP
- RevengeOS
- ... and my eternal friend @Bicet

### For Building
--------

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    apt update
    apt install repo git gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 rsync lib32ncurses-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
    exit

Create BlackIron folder
----------------------------------

    mkdir ~/BlackIron
    cd ~/BlackIron

GIT config (nickname, e-mail)
-----------------------------

    git config --global user.email "mail@domain.com"
    git config --global user.name "login"

To initialize your local repository use
---------------------------------------


### Initialize local repository ###

```bash
repo init -u https://github.com/Black-Iron-Project/manifest -b thirteen
```
 or you can do a shallow clone if you dont't have much bandwidth
```bash
repo init -u https://github.com/Black-Iron-Project/manifest -b thirteen --depth=1
```
Shallow clone lets you pull down just the latest commits, not the entire repo history. So if your project has years of history, or history from thousands of commits, you can select a particular depth to pull.

So if we are providing argument of `-- depth 1` to the repo init command it will copy only the latest revision of a repo.

### Sync ###

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
You can just use `repo sync` or above command, but this will save you from lot of terminal spam, data and time.
```bash
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_$device-userdebug

# Build the code
$ mka bacon -jX
```
