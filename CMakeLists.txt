cmake_minimum_required(VERSION 3.0)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.16.7.tar.gz"
    SHA1 "2b0c02c6fc6a93d2a6f256eb9b3aed9f13f6c5b7"
)

project(caffe_simple_with_hunter)

hunter_add_package(caffe)
find_package(Caffe CONFIG REQUIRED)

add_executable(foo foo.cpp)
target_link_libraries(foo caffe)
