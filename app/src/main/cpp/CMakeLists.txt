# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.
add_executable(rtl_fm_stereo
#        rtl_fm.c
        rtl_fm_stereo.c
        libusb/core.c
        libusb/descriptor.c
        libusb/hotplug.c
        libusb/os/linux_usbfs.c
        libusb/os/poll_posix.c
        libusb/os/threads_posix.c
        libusb/os/linux_netlink.c
        libusb/io.c
        libusb/strerror.c
        libusb/sync.c
        convenience/convenience.c
        getopt/getopt.c
        librtlsdr.c
        #        rtl-sdr-android.c
        tuner_e4k.c
        tuner_fc0012.c
        tuner_fc0013.c
        tuner_fc2580.c
        tuner_r82xx.c)
add_executable(rtl_fm
        rtl_fm.c
        libusb/core.c
        libusb/descriptor.c
        libusb/hotplug.c
        libusb/os/linux_usbfs.c
        libusb/os/poll_posix.c
        libusb/os/threads_posix.c
        libusb/os/linux_netlink.c
        libusb/io.c
        libusb/strerror.c
        libusb/sync.c
        convenience/convenience.c
        getopt/getopt.c
        librtlsdr.c
        #        rtl-sdr-android.c
        tuner_e4k.c
        tuner_fc0012.c
        tuner_fc0013.c
        tuner_fc2580.c
        tuner_r82xx.c)
add_executable(rtl_power
        rtl_power.c
        libusb/core.c
        libusb/descriptor.c
        libusb/hotplug.c
        libusb/os/linux_usbfs.c
        libusb/os/poll_posix.c
        libusb/os/threads_posix.c
        libusb/os/linux_netlink.c
        libusb/io.c
        libusb/strerror.c
        libusb/sync.c
        convenience/convenience.c
        getopt/getopt.c
        librtlsdr.c
        #        rtl-sdr-android.c
        tuner_e4k.c
        tuner_fc0012.c
        tuner_fc0013.c
        tuner_fc2580.c
        tuner_r82xx.c)
add_executable(rtl_fm_streamer
        rtl_fm_streamer.c
        libusb/core.c
        libusb/descriptor.c
        libusb/hotplug.c
        libusb/os/linux_usbfs.c
        libusb/os/poll_posix.c
        libusb/os/threads_posix.c
        libusb/os/linux_netlink.c
        libusb/io.c
        libusb/strerror.c
        libusb/sync.c
        convenience/convenience.c
        getopt/getopt.c
        librtlsdr.c
        jsonrpc-c/jsonrpc-c.c
        jsonrpc-c/cJSON.c
        jsonrpc-c/ev.c
        #        rtl-sdr-android.c
        tuner_e4k.c
        tuner_fc0012.c
        tuner_fc0013.c
        tuner_fc2580.c
        tuner_r82xx.c)
add_library( # Sets the name of the library.
        native-lib

        # Sets the library as a shared library.
        SHARED

        # Provides a relative path to your source file(s).
        native-lib.cpp
        libusb/core.c
        libusb/descriptor.c
        libusb/hotplug.c
        libusb/os/linux_usbfs.c
        libusb/os/poll_posix.c
        libusb/os/threads_posix.c
        libusb/os/linux_netlink.c
        libusb/io.c
        libusb/strerror.c
        libusb/sync.c
        convenience/convenience.c
        getopt/getopt.c
        librtlsdr.c
#        rtl-sdr-android.c
        tuner_e4k.c
        tuner_fc0012.c
        tuner_fc0013.c
        tuner_fc2580.c
        tuner_r82xx.c
        )

# Searches for a specified prebuilt library and stores the path as a
# variable. Because CMake includes system libraries in the search path by
# default, you only need to specify the name of the public NDK library
# you want to add. CMake verifies that the library exists before
# completing its build.

find_library( # Sets the name of the path variable.
        log-lib

        # Specifies the name of the NDK library that
        # you want CMake to locate.
        log)

# Specifies libraries CMake should link to your target library. You
# can link multiple libraries, such as libraries you define in this
# build script, prebuilt third-party libraries, or system libraries.

target_link_libraries( # Specifies the target library.
        native-lib

        # Links the target library to the log library
        # included in the NDK.
        ${log-lib})