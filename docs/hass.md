

### Running Hass.io on an [Intel Nuc](https://www.intel.com/content/www/us/en/products/boards-kits/nuc/kits/nuc5cpyh.html) with Ubuntu Server, in docker.
To run Hass.io this way, [install manually in Docker](https://github.com/home-assistant/hassio-build/blob/master/install/README.md).

* Running a slave instance of Home Assistant on a Raspberry Pi 3 with a 16 gb memory card for better bt range.
* Using native Homekit component to get support for Homekit and Siri.

My configuration is broken down into [packages](https://www.home-assistant.io/docs/configuration/packages/), sort of mini configuration-files. This makes it easy to see everything pertaining to a specific implementation.

Most of my more advanced automations are migrated to Appdaemon apps.