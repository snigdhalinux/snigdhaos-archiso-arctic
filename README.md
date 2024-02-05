<h1 align="center" id="title">Snigdha OS[Build: Arctic]</h1>

!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)(https://www.buymeacoffee.com/SnigdhaOS)

![Static Badge](https://img.shields.io/badge/ISO%20BUILD-STABLE-754ffe)
![GitHub issues](https://img.shields.io/github/issues/snigdhalinux/snigdhaos-archiso-arctic)
![GitHub Downloads (specific asset, latest release)](https://img.shields.io/github/downloads/snigdhalinux/snigdhaos-archiso-arctic/latest/snigdhaos-arctic-v4.5-x86_64.iso)
![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/snigdhalinux/snigdhaos-archiso-arctic/total)
![GitHub Sponsors](https://img.shields.io/github/sponsors/snigdhalinux)
![Website](https://img.shields.io/website?url=https%3A%2F%2Fsnigdhaos.org)


# Build Snigdha OS ISO

To build **Snigdha OS** iso, you will require our `keyring`, `Server Url` and `Repository` as well as the `chaotic aur`.

## Requirements:
- Any Arch Based Linux Distrbution. e.g: `ArchLinux`, `GarudaLinux`, `Manjaro` etc.
- An Active Internet Connection [Stable]
- `snigdhaos-core` & `chaotic-aur`

### Setting Up Keyring for Snigdha OS Core:
First, install the primary key - it can then be used to install our keyring and mirrorlist.
#### Step 1: Receiving Key From Server:
```bash
sudo pacman-key --recv-key 9F2C5C96FE18E143 --keyserver keyserver.ubuntu.com
```
#### Step 2: Locally Signing key:
```bash
sudo pacman-key --lsign-key 9F2C5C96FE18E143
```
#### Step 3: Getting Snigdha OS Keyring:
```bash
sudo pacman -U 'https://github.com/snigdhalinux/snigdhaos-core/blob/master/x86_64/snigdhaos-keyring-3.0-1-any.pkg.tar.zst'
```
#### Step 4: Append (adding to the end of the file) to /etc/pacman.conf:
```bash
[snigdhaos-core]
Server = https://snigdhalinux.github.io/$repo/$arch
```

### Setting Up Chaotic Aur:
```bash
sudo pacman-key --recv-key 3056513887B78AEB --keyserver keyserver.ubuntu.com
```
```bash
sudo pacman-key --lsign-key 3056513887B78AEB
```
```bash
sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-keyring.pkg.tar.zst'
```
```bash
sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-mirrorlist.pkg.tar.zst'
```
Append (adding to the end of the file) to /etc/pacman.conf:
```bash
[chaotic-aur]
Include = /etc/pacman.d/chaotic-mirrorlist
```
***Use your favorite editor to edit `pacman.conf` e.g: `nano`, `vim` etc.**

### Downloading the source:
#### Step 1: Cloning

```bash
git clone https://github.com/snigdhalinux/snigdhaos-archiso-arctic.git
```
Get inside,

```bash
cd snigdhaos-archiso-arctic/build-arctic/
```
Make `build-arctic.sh` as an executable file.
```bash
chmod +x ./build-arctic.sh
```
**In case if it doesn't work,**
```bash
sudo pacman -S archiso
```
or if you are on Snigdha OS, start from here,
```bash
install archiso
```
Get into the directory `snigdhaos-archiso-arctic/` and execute,
```bash
sudo mkarchiso -v -w build/ -o iso/ archiso-arctic/
```
It will start the iso building process. You can add any custom packages of your own. Just edit the `packages.x86_64` and insert your package name. e.g: `visual-studio-code-bin`, `google-chrome`. it will take some time to build depending on your machine. You can have coffee break till it is done. 

After the build process has finished, you will get a new directory **`iso`**. And you will find the Snigdha OS installer iso with name `snigdhaos-arctic-v$current_version-x86_64.iso`. Now you can install it on your machine or you can test it on any virtual machine.

