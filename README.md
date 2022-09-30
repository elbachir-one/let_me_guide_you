# Void Linux Package Installation from Source.

## Let's try installing and configuring and patching the suckless tools through xbps-src.

### Installing and configuring DWM ST Dmenu.


1. Install xorg and git, as well as any additional dependencies such as libXft-devel, libX11-devel, and libXinerama-devel base-devel.

`$ sudo xbps-install -S xorg git base-devel libXft-devel libX11-devel libXinerama-devel`


2. Download the Void packages.

`$ git clone https://github.com/void-linux/void-packages.git`


2. Navigate to the Void packages directory.

`$ cd void-packages`


3. Bootstrap the binary.

`$ ./xbps-src binary-bootstrap`


4. Find the package you want to install, in this case, DWM ST Dmenu.

`$ ls srcpkgs/ | grep dwm`
`$ ls srcpkgs/ | grep st`
`$ ls srcpkgs/ | grep dmenu`


5. Extracting the dwm source code.

`$ ./xbps-src extract dwm`
`$ ls masterdir/builddir/dwm{version}/`


6. Create a files directory within the dwm directory to store the configuration file.

`$ mkdir -p srcpkgs/dwm/files`
`$ cp masterdir/builddir/dwm{version}/config.def.h srcpkgs/dwm/files/config.h`


7. After modifying the config.h for dwm and putting in your config now, it is time to build and install dwm.

`$ ./xbps-src pkg dwm`
`$ sudo xbps-install -R hostdir/binpkgs dwm`


NOTE: If you make another change to the config file, you must force DWM to rebuild and install.

`$ ./xbps-src -f pkg dwm`
`$ sudo xbps-install -R hostdir/binpkgs -f dwm`


### How to patch DWM ST Dmenu.


1. Create a patch directory within the st directory.

`$ mkdir -p srcpkgs/st/patches`


2. Download any patch you want and place it in the patches directory.

`$ ls srcpkgs/st/patches/<patch_name>.diff`


3. Using the patch, as well as building and installing st.

`$ ./xbps-src extract st`
`$ cp masterdir/builddir/st{version}/config.def.h srcpkgs/st/files/config.h`
`$ ./xbps -f pkg st`
`$ sudo xbps-install -R hostdir/binpkgs -f st`


## NOTE: The same is true for other suckless tools.
