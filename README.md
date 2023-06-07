# task1

cmake_minimum_required(VERSION 3.4)
project(formatter)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


add_library(formatter STATIC ./sources/formatter.cpp)
include_directories(./include)

# task2

cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_DIR /home/test/cazakh/workspace/hw/hw_lab3/formatter_ex_lib)

project(formatter_ex)

add_library(formatter_ex STATIC ${CMAKE_DIR}/sources/formatter_ex.cpp)
include_directories(./include)


include_directories(${CMAKE_DIR}/../formatter_lib/include)
target_link_libraries(formatter_ex formatter)

# task3.1

cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_DIR /home/test/cazakh/workspace/hw/hw_lab3/hello_world_application) 

project(hello_world_application)

add_library(hello_world_application ${CMAKE_DIR}/sources/hello_world.cpp)

include_directories(${CMAKE_DIR}/../formatter_ex_lib/include)
target_link_libraries(hello_world_application formatter_ex)

include_directories(${CMAKE_DIR}/../formatter/include)
target_link_libraries(hello_world_application formatter)

# task3.2

cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_DIR /home/test/cazakh/workspace/hw/hw_lab3/formatter_ex_lib)

project(solver)


include_directories(solver ${CMAKE_DIR}/../solver_lib/include)
add_library(solver ${CMAKE_DIR}/../solver_lib/sources/solver.cpp)



include_directories(${CMAKE_DIR}/../formatter_lib/include)
target_link_libraries(solver formatter_ex)
