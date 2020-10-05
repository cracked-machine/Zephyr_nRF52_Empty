# the location of your local Zephyr repo clone. Its quite large so its recommended to keep on a larger disk.
set(ZEPHYR_BASE "/mnt/sda/nRF_Connect_SDK/ncs/zephyr")

# the DeviceTree board definition used by Zephyr. These files are located in the ZEPHYR_BASE/boards/arm repo directory.
set(BOARD "nrf52dk_nrf52832")

# additional KConfig options to enable J-Link RTT.
set(CONF_FILE "prj.conf jlink/jlink_rtt.conf")

# Change this to whatever you want. The output file does NOT use this value but it is still required for CMake to run.
set(PROJECT_NAME, "TEST")

# suppress CMAKE/Zephyr warning: https://github.com/zephyrproject-rtos/zephyr/pull/18777
#set(NO_BUILD_TYPE_WARNING "True")

cmake_minimum_required(VERSION 3.13.1)

# include zephyr cmake script
include(${ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)

project(${PROJECT_NAME})

# settings for J-Link RTT monitoring
set(CMAKE_C_FLAGS "-DNRF_LOG_USES_RTT=1")

target_sources(app PRIVATE   src/main.c )


