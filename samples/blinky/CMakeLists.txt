cmake_minimum_required(VERSION 3.13.1)

include(../../cmake/boilerplate.cmake)
include($ENV{ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)
project(blinky)

target_sources(app PRIVATE src/main.c)
