# cmake_minimum_required(VERSION 3.10)
# project(PhysicsEngine LANGUAGES CXX)

# set(CMAKE_CXX_STANDARD 17)
# set(CMAKE_CXX_STANDARD_REQUIRED ON)
# set(CMAKE_CXX_EXTENSIONS OFF)

# add_subdirectory(external/glfw)

# add_executable(phy main.cpp)

# target_link_libraries(phy PRIVATE glfw)

# find_package(OpenGL REQUIRED)
# target_link_libraries(phy PRIVATE OpenGL::GL)

# # target_compile_options(phy PRIVATE
# #     -Wall -Wextra -Wpedantic
# # )




cmake_minimum_required (VERSION 3.10)
project(PhysicsEngine LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(phy main.cpp)

target_include_directories(phy PRIVATE external/glfw/include)

target_link_libraries(phy PRIVATE
    ${CMAKE_SOURCE_DIR}/external/glfw/lib-vc2022/glfw3.lib
)

find_package(OpenGL REQUIRED)
target_link_libraries(phy PRIVATE OpenGL::GL)

# target_compile_options(phy PRIVATE
#     $$ < $$<CXX_COMPILER_ID:MSVC>:/W4 /permissive- /WX>
# )
