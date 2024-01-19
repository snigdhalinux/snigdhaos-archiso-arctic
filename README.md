
# Snigdha OS - Arctic [Developer Edition🔥]

Snigdha OS has been built for developers with addtional features. During the **Online Installation** a wide range of options will be opend to you and choose according to your necessity what you want to install. But in the **Offline Installation** you will get no choice to install application/tools. But you can download more application later! **Offline Installation** contains minimal apps & tools **e.g. Microsoft Visual Studio Code** as your primary ide and no language supports or extensions preinstalled. - Built by a user like you with ❤️.




## Documentation

![Downloads](https://img.shields.io/github/downloads/snigdhalinux/snigdhaos-archiso-arctic/total) 
![Contributors](https://img.shields.io/github/contributors/snigdhalinux/snigdhaos-archiso-arctic?color=dark-green) 
![Issues](https://img.shields.io/github/issues/snigdhalinux/snigdhaos-archiso-arctic) 
![License](https://img.shields.io/github/license/snigdhalinux/snigdhaos-archiso-arctic) 

### Build Arctic
To build the **Snigdha OS Arctic** iso, at first you will need **snigdhaos keyring**. [N.B: If you are using **Snigdha OS** already then you don't need to install **snigdhaos keyring**.]

#### Step : Installing the keyring
```bash
sudo pacman -U "https://builds.snigdhaos.org/repo/snigdha-core/x86_64/snigdhaos-keyring-2.0-1-any.pkg.tar.zst"
```
#### Step: Add Server to Your pacman.conf
```bash
sudo nano /etc/pacman.conf
```
Append the following lines at the end of pacman.conf.
```bash
[snigdha-core]
Server = https://builds.snigdhaos.org/repo/$repo/$arch

[arctic]
Server = https://builds.snigdhaos.org/repo/$repo/$arch
```
**Caution:** If it says **Invalid Signature** then you can use following methods to resolve.
#### Method 1 : initiating & populating pacman-key
```bash
sudo pacman-key --init snigdhaos
```
```bash
sudo pacman-key --populate snigdhaos
```
*If not resolved,*
#### Method 2 : Set The SigLevel ⇒ Never  

```bash
[snigdha-core]
SigLevel = Never
Server = https://builds.snigdhaos.org/repo/$repo/$arch

[arctic]
SigLevel = Never
Server = https://builds.snigdhaos.org/repo/$repo/$arch
```

