cmake_minimum_required(VERSION 3.17)

set(CMAKE_CXX_STANDARD 11)

set(GOOGLETEST_VERSION 1.10.0)

add_subdirectory(googletest/)

set(gtest_DIR, googletest/)
include_directories(${gtest_DIR}/include ${gtest_DIR})

set(SOURCES_TESTS mainTests.cpp Movement.h Collisions.h)

add_executable(test ${SOURCES_TESTS})
find_package(SFML 2 COMPONENTS network audio graphics window system REQUIRED)

target_link_libraries(test gtest gtest_main RPG_game_Tests sfml-graphics sfml-window sfml-system)