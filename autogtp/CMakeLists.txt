cmake_minimum_required(VERSION 3.16)

# 设置项目名称
project(autogtp)

# 启用 Qt6 自动 MOC 支持
set(CMAKE_AUTOMOC ON)

# 查找 Qt6 库
find_package(Qt6 REQUIRED COMPONENTS Core)

# 设置源文件
add_executable(autogtp
    Game.h Order.h Management.h Worker.h Job.h Result.h Console.h
    Worker.cpp Management.cpp Job.cpp main.cpp Game.cpp Order.cpp
)

# 启用 Qt6 的自动 MOC 支持
set_target_properties(autogtp PROPERTIES AUTOMOC 1)

# 链接 Qt6 库
target_link_libraries(autogtp Qt6::Core)

# 安装可执行文件
install(TARGETS autogtp DESTINATION ${CMAKE_INSTALL_BINDIR})
