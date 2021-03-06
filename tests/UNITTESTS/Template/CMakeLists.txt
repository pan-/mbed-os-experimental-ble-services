# Copyright (c) 2020 ARM Limited. All rights reserved.
# SPDX-License-Identifier: Apache-2.0
cmake_minimum_required(VERSION 3.0.2)

# remember to change the name of the test
set(TEST_NAME ble-service-template-unittest)

add_executable(${TEST_NAME})

target_include_directories(${TEST_NAME}
    PRIVATE
        .
        # Includes needed by your test, for example the service you're testing
        # ${SERVICES_PATH}/Template/include
)

target_sources(${TEST_NAME}
    PRIVATE
        test_Template.cpp
        # add any source files here that need to be built for the test, for example the service you're testing
        # ${SERVICES_PATH}/Template/Template.cpp
)

target_link_libraries(${TEST_NAME}
    PRIVATE
        # add any stubs, mocks or fakes you need here
        mbed-os-fakes-ble
        mbed-os-fakes-event-queue
        # these are libraries that provided include paths of real mbed-os headers
        mbed-os-headers-base
        mbed-os-headers-platform
        # if you're using googletest this is required
        gmock_main
)

add_test(NAME "${TEST_NAME}" COMMAND ${TEST_NAME})
