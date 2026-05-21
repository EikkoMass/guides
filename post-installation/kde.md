# Post Installation on KDE

## General Use

### Software Store

If your software store is missing on your system, you can install it with the command:

It'll require that the `flatpak` package is installed too, so you may need to install it first.

```bash
sudo pacman -S flatpak discover
```

### AppImages

On a fresh install maybe you tried to run an AppImage and nothing happened. You may need to install additional dependencies to make it work.

```bash
sudo pacman -S fuse2
```

If your app seems to be broken or slow, take a look if it requires additional permissions (can be executed, can read/write files, etc.).

### Screenshots

The KDE ecosystem already provides an really good screenshot app called `spectacle`, you can install it with the command:

```bash
sudo pacman -S spectacle
```

### File Compression and Decompression

You can use the `zip` and `tar` commands to compress and decompress files.

```bash
sudo pacman -S zip tar
```

## Bluetooth

Bluetooth is a wireless technology that allows devices to connect and share data over short distances. Really Useful indeed.

To make this work with KDE, you'll need to install a ton of dependencies (some of them to make it work or 
integrate properly with the display manager). You can install them with the command:

```bash
sudo pacman -S bluedevil bluez-deprecated-tools bluez-utils
```

## Internet & Networking

If your network icon is missing on your system tray, missing on system settings or wifi not working properly, maybe you need to install 
the `plasma-nm` package:

```bash
sudo pacman -S plasma-nm
```

## Media Player

You can use a good variety of media players, in this case I prefer for `vlc` and `mpv`, you can install with the command:

```bash
sudo pacman -S vlc mpv
```

Probably your vlc will not work with mp4 files, so you may need to install additional codecs with the command:

```bash
sudo pacman -S vlc-plugin-ffmpeg
```


## Audio

### Audio Manager Tray Icon

If your audio manager are missing on
your system tray, you must install `plasma-pa` by running the following command:

```bash
sudo pacman -S plasma-pa
```

### Compatibility on managing volume with keyboard keys

Usually this happens because you choosed pipewire, but to make this work you'll need to 
install a compatilibity package called `pipewire-alsa`, who'll provide the ALSA compatibility layer for PipeWire.

```bash
sudo pacman -S pipewire-alsa wireplumber
```
