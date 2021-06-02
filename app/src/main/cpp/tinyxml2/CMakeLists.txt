##最低版本号要求##
##cmake_minimum_required (VERSION 2.8)

##project info##
set(PACKAGE_NAME tinyxml2)

#------------------------------------------[0]----------------------------------------------------#
####库文件的默认输出路径，这里设置为工程目录下的lib目录
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY
        ${PROJECT_SOURCE_DIR}/android/${ANDROID_ABI}/lib)
#-------------------------------------------------------------------------------------------------#

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

include_directories(${PROJECT_SOURCE_DIR}/tinyxml2/include)

add_library( # Sets the name of the library.
        ${PACKAGE_NAME}

        # Sets the library as a shared library.
        SHARED

        # Provides a relative path to your source file(s).
        src/tinyxml2.cpp )


# Searches for a specified prebuilt library and stores the path as a
# variable. Because CMake includes system libraries in the search path by
# default, you only need to specify the name of the public NDK library
# you want to add. CMake verifies that the library exists before
# completing its build.

find_library( # Sets the name of the path variable.
        log-lib

        # Specifies the name of the NDK library that
        # you want CMake to locate.
        log )

# Specifies libraries CMake should link to your target library. You
# can link multiple libraries, such as libraries you define in this
# build script, prebuilt third-party libraries, or system libraries.

target_link_libraries( # Specifies the target library.
        ${PACKAGE_NAME}

        # Links the target library to the log library
        # included in the NDK.
        ${log-lib} )