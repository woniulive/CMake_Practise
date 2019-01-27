#This is comment

#set minimum cmake version to build this project
cmake_minimum_required (VERSION 2.8)

#set project name
project (Cmake_Practise)

#set main.c to another name
SET (SRC_LIST main.c)

#print message
MESSAGE(STATUS "This is BINARY dir " ${Cmake_Practise_BINARY_DIR})
MESSAGE(STATUS "This is SOURCE dir " ${Cmake_Practise_SOURCE_DIR})

#compile main.c to execcutale main file
add_executable(main ${SRC_LIST})
