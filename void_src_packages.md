# How to Install Packages From Source on Void Linux.

In this example let me try installing the TorBrowser.


1. Go to the github page for Void Linux and download the Void source packages collection.

`$ git clone https://github.com/void-linux/void-packages.git`

Note: Make sure that you have git.


2. Change directory to Void packages.

`$ cd void-packages/`


3. Bootstrap the binary.

`$ ./xbps-src binary-bootstrap`


4. Install the package you want, in this case TorBrowser.

`$ ls srcpkgs/ | grep torbrowser`

`$ ./xbps-src pkg torbrowser-launcher`

`$ cd`

`$ sudo xbps-install --repository=/home/<your username>/void-packages/hostdir/binpkgs/ torbrowser-launcher`


5. Go to your applications and find the Tor browser.

Thank You.
