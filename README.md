# Black Iron Project #
<p align="center">
<img src="https://github.com/Black-Iron-Project/manifest/blob/sixteen/BLKI_banner.png">
</p>

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
repo init -u https://github.com/Black-Iron-Project/manifest -b sixteen --git-lfs
```
### Sync ###

```bash
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

- Set up the build environment
```bash
source build/envsetup.sh
```

- Lunch a target
```bash
lunch blackiron_$devicecodename-bp2a-userdebug
```

- To start compiling
```bash
mka blackiron -j$(nproc --all)
```
