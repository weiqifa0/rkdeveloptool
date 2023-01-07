rkdeveloptool gives you a simple way to read/write rockusb device.let's start.

compile and install
1 install libusb and libudev
	sudo apt-get install libudev-dev libusb-1.0-0-dev dh-autoreconf
2 go into root of rkdeveloptool
3.aclocal
4.autoreconf -i
5.autoheader
5.automake --add-missing
4 ./configure
5 make

rkdeveloptool usage,input "rkdeveloptool -h" to see

example:
1.download kernel.img
sudo ./rkdeveloptool db RKXXLoader.bin    //download usbplug to device
sudo ./rkdeveloptool wl 0x8000 kernel.img //0x8000 is base of kernel partition,unit is sector.
sudo ./rkdeveloptool rd                   //reset device

compile error help
if you encounter the error like below:
./configure: line 4269: syntax error near unexpected token `LIBUSB1,libusb-1.0'
./configure: line 4269: `PKG_CHECK_MODULES(LIBUSB1,libusb-1.0)'

You should install pkg-config libusb-1.0:
	sudo apt-get install pkg-config libusb-1.0 


# 在MacBook上是如何安装的呢？
* brew install automake 

安装libusb
https://macappstore.org/libusb/

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
brew install libusb
brew install libudev

以及pkgconfig安装
https://ports.macports.org/port/pkgconfig/#:~:text=To%20install%20pkgconfig%2C%20paste%20this%20in%20macOS%20terminal,installing%20MacPorts%20sudo%20port%20install%20pkgconfig%20More%20instructions

