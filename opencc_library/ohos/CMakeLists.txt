# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

SET(CMAKE_BUILD_WITH_INSTALL_RPATH TRUE)

project(flutter_opencc_ffi_ohos_library VERSION 0.0.1 LANGUAGES C)

add_subdirectory(../OpenCC build)

set(OPENCC_TARGET libopencc)

target_sources(${OPENCC_TARGET} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../interface.cpp ${CMAKE_CURRENT_SOURCE_DIR}/../interface.def)


#add_library(flutter_opencc_ffi_ohos SHARED
#  "flutter_opencc_ffi_ohos.c"
#)
#
#set_target_properties(flutter_opencc_ffi_ohos PROPERTIES
#  PUBLIC_HEADER flutter_opencc_ffi_ohos.h
#  OUTPUT_NAME "flutter_opencc_ffi_ohos"
#)
#
#target_compile_definitions(flutter_opencc_ffi_ohos PUBLIC DART_SHARED_LIB)
