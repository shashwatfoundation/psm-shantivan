# psm-shantivan

1) bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)
2) sudo systemctl enable nodered.service
3) sudo apt-get install libudev-dev libusb-1.0-0-dev git
4) cd .node-red
5) npm i node-red-contrib-usbhid-reader
6) sudo mkdir -p /etc/udev/rules.d
7) sudo nano /etc/udev/rules.d/51-blink1.rules
8) copy following content

SUBSYSTEM=="input", GROUP="input", MODE="0777"
SUBSYSTEM=="usb", MODE:="777", GROUP="plugdev"
KERNEL=="hidraw*", MODE="0777", GROUP="plugdev"

9) sudo udevadm control --reload-rules
10) sudo groupadd -f input
11) sudo gpasswd -a $USER input

