CMAKE_MINIMUM_REQUIRED (VERSION 2.6)
PROJECT (D7AOSS C)

#######################################
# Configuration
#######################################
SET(D7AOSS_PHY_RADIO_DRIVER "CC430" CACHE STRING "Radio chip driver used by PHY")
SET_PROPERTY(CACHE D7AOSS_PHY_RADIO_DRIVER PROPERTY STRINGS CC430 STUB)

SET(D7AOSS_HAL_DRIVER "CC430" CACHE STRING "HAL implementation")
SET_PROPERTY(CACHE D7AOSS_HAL_DRIVER PROPERTY STRINGS CC430 STUB)

OPTION(D7AOSS_BUILD_TESTS BOOL "Build tests")

OPTION(D7AOSS_BUILD_EXAMPLES BOOL "Build examples")

#######################################
# Modules
#######################################
ADD_SUBDIRECTORY(d7aoss)

IF(D7AOSS_BUILD_EXAMPLES)
    ADD_SUBDIRECTORY(examples)
ENDIF()

IF(D7AOSS_BUILD_TESTS)
    ADD_SUBDIRECTORY(tests)

ENDIF()


