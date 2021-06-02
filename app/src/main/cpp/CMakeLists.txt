# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.10.2)

# Declares and names the project.

project("ysos_libs_as81")

#  Add lib directories for cmake
## libjson.so ##
add_subdirectory(json)

## libtinyxml2.so ##
add_subdirectory(tinyxml2)