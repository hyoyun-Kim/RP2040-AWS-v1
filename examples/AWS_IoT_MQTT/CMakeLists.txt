add_executable(AWS_IoT_MQTT
        AWS_IoT_MQTT.c
    )

target_include_directories(AWS_IoT_MQTT PUBLIC
        ${CMAKE_SOURCE_DIR}/libraries/ioLibrary_Driver/Ethernet
        ${CMAKE_SOURCE_DIR}/libraries/ioLibrary_Driver/Internet/dhcp
        ${CMAKE_SOURCE_DIR}/libraries/ioLibrary_Driver/Internet/dns
        ${CMAKE_SOURCE_DIR}/libraries/mbedtls/include
        ${CMAKE_SOURCE_DIR}/libraries/mbedtls/library
        ${CMAKE_SOURCE_DIR}/interface
        )

target_link_libraries(AWS_IoT_MQTT PUBLIC
        pico_stdlib
        hardware_spi
        hardware_dma
        ETHERNET_FILES
        DHCP_FILES
        DNS_FILES
        INTERFACE_FILES
        mbedcrypto
        mbedx509
        mbedtls
        )

#pico_enable_stdio_usb(AWS_IoT_MQTT 1)
#pico_enable_stdio_uart(AWS_IoT_MQTT 0)

pico_add_extra_outputs(AWS_IoT_MQTT)
