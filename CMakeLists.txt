cmake_minimum_required(VERSION 3.0)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.16.5.tar.gz"
    SHA1 "51594bfe1f58a7264c811a0d84bea79fc6758d6b"
)

project(caffe_simple_with_hunter)

hunter_add_package(caffe)
find_package(Caffe CONFIG REQUIRED)

add_executable(foo foo.cpp)
target_link_libraries(foo caffe)
