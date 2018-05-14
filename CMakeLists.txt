cmake_minimum_required(VERSION 2.8)

PROJECT (colormatchTemplate)

find_package(OpenCV  REQUIRED)


file(GLOB colormatchTemplate_SRCS
    "*.h"
    "*.cpp")
ADD_EXECUTABLE (colormatchTemplate ${colormatchTemplate_SRCS})



if (OpenCV_FOUND)
	include_directories( ${OpenCV_INCLUDE_DIRS} )
	target_link_libraries( colormatchTemplate ${OpenCV_LIBS} )
else (OpenCV_FOUND)
message("PB->OPENCV = ${OpenCV_INCLUDE_DIRS}")
endif (OpenCV_FOUND)

