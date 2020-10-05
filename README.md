### Blinky example for nRF52/Zephyr using CMake/GNU/J-Link + VSCode/CortexDebug

This is an example of how to develop a zephyr app for nRF52832 *outside* of the Zephyr repo tree. See [Zephyr App Dev Primer](https://docs.zephyrproject.org/1.13.0/application/application.html)

Copy your source files into `src` and add the required KConfig options into `prj.conf`.

- You must have a Zephyr repository somewhere on your PC. However, `West` is not required to build/run/debug this project.
- ZEPHYR_BASE, BOARD and CONF_FILE are set locally in the CMakeLists.txt file.
- Building: [CMake](https://code.visualstudio.com/docs/cpp/cmake-linux)/[Ninja](https://ninja-build.org/).
- Debug: JLinkGDBServerCLExe (`.vscode/launch.json`) and [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug)
- Terminal I/O: JLinkRTTClient (run in terminal before starting debugger)
- Direct flash program: JLinkExe (`jlink/flash.sh`).

Note, RTT monitor config in `CMakeLists.txt` and `jlink/jlink_rtt.conf`. More info: [Serial output with JLinkRTTClient on the nRF52-DK with Zephyr](https://bitshiftjo.cluster026.hosting.ovh.net/2020/10/03/serial-output-with-jlinkrttclient-on-the-nrf52-dk-with-zephyr/)

