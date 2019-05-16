cmake_minimum_required(VERSION 3.7)
project(PCN)

# OpenCV
find_package(OpenCV REQUIRED)

# blas
if(APPLE)
    include_directories(/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/System/Library/Frameworks/Accelerate.framework/Versions/A/Frameworks/vecLib.framework/Headers)
endif(APPLE)

FILE(GLOB_RECURSE SOURCES crop.cpp fddb.cpp PCN.cpp video.cpp)
FILE(GLOB_RECURSE HEADERS PCN.h)

add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})
