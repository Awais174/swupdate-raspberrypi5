# swupdate-raspberrypi5

This setup is verified on Poky Scarthgap 5.0.14 branch with Raspberry Pi 5.

Please follow 'Yocto Project Quick Build' for Scarthgap 5.0.14: https://docs.yoctoproject.org/5.0.14/brief-yoctoprojectqs/index.html

$ git clone -b scarthgap git://git.yoctoproject.org/poky

$ cd poky


Clone required additional layers:

$ git clone -b scarthgap https://github.com/openembedded/meta-openembedded

$ git clone https://github.com/Awais174/meta_rpi_network

$ git clone -b dev/rpi5 https://github.com/Awais174/meta-swupdate-boards

$ git clone -b scarthgap https://github.com/sbabic/meta-swupdate

$ git clone -b scarthgap https://github.com/agherzan/meta-raspberrypi

$ source oe-init-build-env


Replace the generated build folder with the 'build' folder provided in this repo to use pre-configure BBLAYER file and quickly build for rpi, rpi4 or rpi5 using bitbake multiconfig. Alternatively, you can manually update the generated build/bblayers.conf and local.conf using the template provided in provided 'build' folder, to build swupdate layer.

Move all additional layers inside poky folder.

$ bitbake mc:rpi5:update-image
