list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/eil-cmake-utils/cmake)
include(eil_check_idf_features)
eil_check_idf_has_esp_drivers()

set(REQUIRED_COMPONENTS log)

if(EIL_IDF_HAS_ESP_DRIVERS)
    list(APPEND REQUIRED_COMPONENTS esp_driver_gpio esp_driver_spi)
else()
    list(APPEND REQUIRED_COMPONENTS driver)
endif()

idf_component_register(
    SRCS max7219.c
    INCLUDE_DIRS .
    REQUIRES ${REQUIRED_COMPONENTS}
)

include(eil_ci)
