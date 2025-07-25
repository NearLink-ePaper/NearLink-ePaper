#===============================================================================
# @brief    cmake file
# Copyright (c) CompanyNameMagicTag 2023-2023. All rights reserved.
#===============================================================================
set(COMPONENT_NAME "samples")

set(SOURCES
)

set(PUBLIC_HEADER
)

if(DEFINED CONFIG_ENABLE_PERIPHERAL_SAMPLE)
    add_subdirectory_if_exist(peripheral)
endif()
if(DEFINED CONFIG_ENABLE_WIFI_SAMPLE)
    add_subdirectory_if_exist(wifi)
endif()
if(DEFINED CONFIG_ENABLE_PRODUCTS_SAMPLE)
    add_subdirectory_if_exist(products)
endif()
if(DEFINED CONFIG_ENABLE_EPAPER_SAMPLE)
    add_subdirectory_if_exist(ePaper)
endif()
if(DEFINED CONFIG_ENABLE_TOUCH_SCREEN_SAMPLE)
    add_subdirectory_if_exist(TouchScreen)
endif()
if(DEFINED CONFIG_ENABLE_MQTT_SAMPLE)
    add_subdirectory_if_exist(MQTT)
endif()

add_subdirectory_if_exist(custom)

set(PRIVATE_HEADER
)

set(PRIVATE_DEFINES
)

set(PUBLIC_DEFINES
)

# use this when you want to add ccflags like -include xxx
set(COMPONENT_PUBLIC_CCFLAGS
)

# 设置不显示不使用警告
set(COMPONENT_CCFLAGS
    -Wno-unused-variable
    -Wno-unused-parameter
    -Wno-error=unused-function
)

set(WHOLE_LINK
    true
)

set(MAIN_COMPONENT
    false
)

install_sdk("${CMAKE_CURRENT_SOURCE_DIR}/peripheral" "*")
install_sdk("${CMAKE_CURRENT_SOURCE_DIR}/products" "*")
install_sdk("${CMAKE_CURRENT_SOURCE_DIR}/wifi/sta_sample" "*")
install_sdk("${CMAKE_CURRENT_SOURCE_DIR}/wifi/softap_sample" "*")

build_component()
