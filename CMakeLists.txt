cmake_minimum_required(VERSION 3.10)
project(server)

set(CMAKE_CXX_STANDARD 17)
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}")

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

find_package(Threads REQUIRED)
find_package(Boost 1.70 REQUIRED COMPONENTS system filesystem program_options)
find_package(TBB REQUIRED)
set(Boost_USE_MULTITHREADED ON)
include_directories(${Boost_INCLUDE_DIRS})

set(ADDITIONAL_LIBRARIES "")
if(MINGW)
    set(ADDITIONAL_LIBRARIES ${ADDITIONAL_LIBRARIES} -lws2_32 -lwsock32)
elseif(MSVC)
    set(ADDITIONAL_LIBRARIES ${ADDITIONAL_LIBRARIES} ws2_32.lib wsock32.lib)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /D_WIN32_WINNT=0x0601 /D_SILENCE_CXX17_ALLOCATOR_VOID_DEPRECATION_WARNING")
endif()

include_directories(./inc)
add_library(http SHARED inc/http.h src/http.cpp src/casher.cpp inc/cli.h src/cli.cpp ${Boost_LIBRARIES})

add_executable(async src/async.cpp)
add_executable(sync src/sync.cpp)
target_link_libraries(async Threads::Threads  ${ADDITIONAL_LIBRARIES} http ${Boost_LIBRARIES} TBB::tbb TBB::malloc TBB::malloc_proxy)
target_link_libraries(sync Threads::Threads ${ADDITIONAL_LIBRARIES} http ${Boost_LIBRARIES} TBB::tbb TBB::malloc TBB::malloc_proxy)

add_executable(coro src/coro.cpp)
target_link_libraries(coro Threads::Threads  ${ADDITIONAL_LIBRARIES} http ${Boost_LIBRARIES} TBB::tbb TBB::malloc TBB::malloc_proxy)
