# NanoC6 Zigbee Project

- IDF v5.2-beta2 tag
- commit: b4a612345be8fa70be8321a6a491baf813a74c4d

## Setting up the Repositories

### IDF v5.2


    git clone --recursive https://github.com/espressif/esp-idf.git
    cd esp-idf
    git checkout v5.2.2
    git submodule update --init --recursive
    ./install.sh
    source ./export.sh
    cd ..

### esp-zigbee-sdk
Cloning esp-zigbee-sdk:

    git clone https://github.com/espressif/esp-zigbee-sdk.git

## Build

    end_device/env_sensor
    idf.py build
    cd build/
    esptool.py --chip ESP32 merge_bin -o env_sensor-merged-flash.bin @flash_args 

![pic_01](./assets/pic_01.jpg)

