#This is comment

#If you feel cmake output file is too much,
#just create a new folder named build
#use cmake .. in ./build folder rather than cmake . in root folder
#then you will find all cmake output folder locate in ./build folder
 
#set minimum cmake version to build this project
cmake_minimum_required (VERSION 2.8)

#set project name
project (Cmake_Practise)

#set main.c to another name
#SET (SRC_LIST main.c)

#print message
MESSAGE(STATUS "This is BINARY dir " ${Cmake_Practise_BINARY_DIR})
MESSAGE(STATUS "This is SOURCE dir " ${Cmake_Practise_SOURCE_DIR})

#add sub dir, src means source_dir while bin means output folder
#in this case, src means ./src. bin means ./bin if you use cmake .
#while meaning ./build/bin while use cmake .. in build folder
ADD_SUBDIRECTORY(src bin)

#add sub dir:lib
ADD_SUBDIRECTORY(lib)

#add sub dir:libnoprefix
ADD_SUBDIRECTORY(libnoprefix)

#compile main.c to execcutale main file
#add_executable(main ${SRC_LIST})
