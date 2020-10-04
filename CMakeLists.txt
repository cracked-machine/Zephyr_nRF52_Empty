# SPDX-License-Identifier: Apache-2.0
set(ZEPHYR_BASE "/mnt/sda/nRF_Connect_SDK/ncs/zephyr")
set(BOARD "nrf52dk_nrf52832")
set(CONF_FILE "prj.conf jlink/jlink_rtt.conf")

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


