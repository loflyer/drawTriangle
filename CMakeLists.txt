cmake_minimum_required(VERSION 3.10)
project(drawtriangle LANGUAGES C CXX)


set(Includes "D:/code/openGL/Includes") #  头文件目录
set(staticlib "D:/code/openGL/Libs")  #  静态库文件目录

message("路径"  ${CMAKE_CURRENT_SOURCE_DIR})
# 源文件的位置
file(GLOB SRCLIST  ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp  ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c )


# 包含头文件
include_directories(${PROJECT_SOURCE_DIR}/include  
${Includes} )

# 设置二进制文件输出路径
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)

# 包含静态库路径
link_directories(${staticlib})

# 链接静态库 libcal.a 掐头去尾
link_libraries(glfw3)

# 指定源文件
add_executable(drawtriangle ${SRCLIST})