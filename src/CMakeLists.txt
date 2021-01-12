
aux_source_directory(${PROJECT_SOURCE_DIR}/src MAIN_SRC)

# 用到的包含列表
set(USE_INCLUDE ${PROJECT_SOURCE_DIR}/src/
                ${PROJECT_SOURCE_DIR}/src/include/)


# 平台判断
MESSAGE(STATUS "operation system is ${CMAKE_SYSTEM}")
 
IF (CMAKE_SYSTEM_NAME MATCHES "Linux")
    MESSAGE(STATUS "current platform: Linux ")

    # 用到的库列表
    set(USE_LIBS ${PROJECT_SOURCE_DIR}/lib/libglfw3.a 
        GL m dl X11 pthread)

ELSEIF (CMAKE_SYSTEM_NAME MATCHES "Windows")
    MESSAGE(STATUS "current platform: Windows")
ELSEIF (CMAKE_SYSTEM_NAME MATCHES "FreeBSD")
    MESSAGE(STATUS "current platform: FreeBSD")
ELSE ()
    MESSAGE(STATUS "other platform: ${CMAKE_SYSTEM_NAME}")
ENDIF (CMAKE_SYSTEM_NAME MATCHES "Linux")
 
# if(WIN32)
#     message("windows")
# elseif(APPLE)
#     message("apple")
# elseif(UNIX)
#     message("unix")
# else()
#     message("other")
# endif()


# 包含库的目录
include_directories(${USE_INCLUDE})

# 输出设置
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

# 添加输出
add_executable(${PROJECT_NAME} ${MAIN_SRC})

# 链接库
target_link_libraries(${PROJECT_NAME} ${USE_LIBS})
