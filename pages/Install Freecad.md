# Install FreeCAD

If you have a Windows PC, a Linux PC or a MAC you can obtain the latest version of FreeCAD from [here](https://www.freecad.org/downloads.php?lang=en) There are installers for all these platforms. 

## Rasbperry Pi installation

If you have a Raspberry Pi things are a little trickier. The most recent versions of FreeCAD have yet to be built for the platform. You can have a go at building it yourself, but this is not a job for the faint hearted (and it takes overnight to build the program). You can get version 0.20.2 very easily:

```
sudo apt update
sudo apt upgrade
sudo apt install freecad
```
The above commands install Version 0.20.2 from 2023 and this works OK. 
### Version 1.0.2 on Raspberry Pi

![screenshot of FreeCAD 1.0.2 running on a Raspberry Pi desktop](/images/install/running%20on%20pi.png)
If you want the latest version (1.0.2) you have to do a bit more work and install Flatpak. Flatpak is a Linux app packaging and sandboxing system that lets developers ship applications with their dependencies so they run consistently across different distributions. Flatpak works well, but it does increase the size of installed applications. Make sure you have around 4G of disk space free before installing.  These are the steps you follow to install Flatpak and FreeCAD. 
```
sudo apt update
sudo apt install -y flatpak

sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

sudo flatpak install -y --system flathub org.freecad.FreeCAD

flatpak run org.freecad.FreeCAD
```
This should start up FreeCAD 10 on your Pi running within Flatpak. If you reboot the Pi you will find that FreeCAD shortcuts have been added to the Education and Graphics program groups. If you've already installed version 0.20.2 you can install version 1.0.2 alongside it. 

## Flatpak management
Note that Flatpak applications are not managed in the same way as those installed using apt. These commands might be useful.
```
# List flatpaks
flatpak list

# Update just flatpaks
flatpak update

# Uninstall FreeCAD (Flatpak) if you ever want to
flatpak uninstall org.freecad.FreeCAD
```
