# NanoC6 Zigbee Project

![pic_01](./assets/pic_01.jpg)

## Setting up the Repositories

### IDF v5.2.2

commit: 3b8741b172dc951e18509698dee938304bcf1523

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

### Zigbee gateway

    cd oordinator/esp_zigbee_gateway
    cd components
    rm -rf LovyanGFX
    git clone https://github.com/lovyan03/LovyanGFX
    cd ..
    idf.py build
    cd build/
    esptool.py --chip ESP32 merge_bin -o zigbee_gateway-merged-flash.bin @flash_args 
    
### Zigbee Env sensor

    cd end_device/env_sensor
    idf.py build
    cd build/
    esptool.py --chip ESP32 merge_bin -o env_sensor-merged-flash.bin @flash_args 


