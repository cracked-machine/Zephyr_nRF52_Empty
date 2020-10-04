### Blinky example for nRF52/Zephyr using CMake/GNU/J-Link + VSCode/CortexDebug

Copy your source files into `src` and add the required KConfig options into `prj.conf`.

- This is an example of how to run a zephyr application *outside* of the Zephyr repo tree. See [Zephyr App Dev Primer](https://docs.zephyrproject.org/1.13.0/application/application.html)
- It does not use West.
- ZEPHYR_BASE, BOARD and CONF_FILE are set locally in the CMakeLists.txt file.
- Building: CMake/Ninja (`CMakeLists.txt` and Cortex-Debug).
- Debug: JLinkExe (`.vscode/launch.json`).
- Terminal I/O: JLinkRTTClient (run in terminal before starting debugger)
- RunNoDebug: JLinkExe (`jlink/flash.sh`).

Note, RTT monitor config in `CMakeLists.txt` and `jlink/jlink_rtt.conf`. More info: [Serial output with JLinkRTTClient on the nRF52-DK with Zephyr](https://bitshiftjo.cluster026.hosting.ovh.net/2020/10/03/serial-output-with-jlinkrttclient-on-the-nrf52-dk-with-zephyr/)

