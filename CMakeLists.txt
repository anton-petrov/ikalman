CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

PROJECT(ikalman C)

ENABLE_TESTING()

SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} --std=c99")

# Shared and static libraries

set(srcs gps.c kalman.c matrix.c)
add_library(ikalman SHARED ${srcs})
add_library(ikalman-static STATIC ${srcs})
set_target_properties(ikalman-static PROPERTIES OUTPUT_NAME "ikalman")

# Tests

#add_executable(gps_test gps_test.c)
#add_executable(kalman_test kalman_test.c)
#add_executable(matrix_test kalman_test.c)

#target_link_libraries(gps_test m ikalman-static)
#target_link_libraries(kalman_test m ikalman-static)
#target_link_libraries(matrix_test m ikalman-static)

#add_test(NAME gps_test COMMAND gps_test)
#add_test(NAME kalman_test COMMAND kalman_test)
#add_test(NAME matrix_test COMMAND matrix_test)

#file(COPY testdata DESTINATION .)
