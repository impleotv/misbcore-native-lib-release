cmake_minimum_required(VERSION 3.0.0)
project(misbCoreNativeTest VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(misbCoreNativeTest main.cpp)
set_target_properties(misbCoreNativeTest PROPERTIES ENABLE_EXPORTS 1) 

target_link_libraries(misbCoreNativeTest ${CMAKE_DL_LIBS})



set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

