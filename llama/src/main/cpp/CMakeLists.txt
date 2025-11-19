# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html.
# For more examples on how to use CMake, see https://github.com/android/ndk-samples.

cmake_minimum_required(VERSION 3.22.1)

project("llama-android")

# Local llama.cpp subdirectory (folder postoji u repo-u, naši flagovi su tu)
add_subdirectory(llama.cpp build-llama)

add_library(${CMAKE_PROJECT_NAME} SHARED
    llama-android.cpp)

target_link_libraries(${CMAKE_PROJECT_NAME}
    llama
    common
    android
    log)
