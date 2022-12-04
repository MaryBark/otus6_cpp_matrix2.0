#cmake_minimum_required(VERSION 3.5)

#project(otus6_cpp_martix LANGUAGES CXX)

#set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)

#add_executable(otus6_cpp_martix main.cpp)


cmake_minimum_required(VERSION 3.2)

project(otus6_cpp_martix VERSION 0.0 ${PATCH_VERSION})

#project(otus_cpp6_matrix LANGUAGES CXX)

#set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)

#add_executable(otus_cpp6_matrix main.cpp TwoDimensDisMatrix.h TwoDimensDisMatrix.cpp ProxyPattern.h ProxyPattern.cpp)

configure_file(version.h.in version.h)

add_executable(otus6_cpp_martix main.cpp
    matrix.h
    proxy.h)

set_target_properties(otus6_cpp_martix PROPERTIES
        CXX_STANDART 14
        CXX_STANDART_REQUIRED ON
        COMPILE_OPTION -Wpedantic -Wall -Wextra
        )

install(TARGETS otus6_cpp_martix RUNTIME DESTINATION bin)

set(CPACK_GENERATOR DEB)

set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")

# не знаю, на фига это надо, но в первой лекции было
set(CPACK_PACKAGE_CONTACT Alttaira@yandex.ru)

# тесты сжедаю потом ко всем заданиям, когда до них доползу)))
include(CPack)
