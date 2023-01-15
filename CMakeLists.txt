cmake_minimum_required(VERSION 3.14)
project(Soundex)

set(CMAKE_CXX_STANDARD 14)

enable_testing()

set(sources
    Main.cpp
    SoundexTest.cpp)

add_executable(SoundexTest ${sources})

find_package(GTest CONFIG REQUIRED)

target_link_libraries(
    SoundexTest
    GTest::gmock_main
    GTest::gtest
)

include(GoogleTest)
gtest_discover_tests(SoundexTest)