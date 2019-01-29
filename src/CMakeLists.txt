#in order to use lib, we should include its folder
INCLUDE_DIRECTORIES(../lib/ ../libnoprefix/)

#line below is used for TARGET_LINK_LIBRARIES(main libsample.so)
LINK_DIRECTORIES(${Cmake_Practise_SOURCE_DIR}/build/lib/lib)

#line below is used for TARGET_LINK_LIBRARIES(main :noprefix.a)
LINK_DIRECTORIES(${Cmake_Practise_SOURCE_DIR}/build/libnoprefix/libnoprefix)

ADD_EXECUTABLE(main main)

#mainwhile, we should add lib
#but noitce:it should add after ADD_EXECUTABLE
#TARGET_LINK_LIBRARIES(main sample)

#it is same as TARGET_LINK_LIBRARIES(main sample)
#but if you want use this command,you should do things below:
#1.add LINK_DIRECTORIES(lib dir) before ADD_EXECUTABLE,like 
#LINK_DIRECTORIES(${Cmake_Practise_SOURCE_DIR}/build/lib/lib) defined above
#2.build the lib first
#after run cmake .. in build folder,
#enter ./build/lib and run make to generate lib file first
TARGET_LINK_LIBRARIES(main libsample.so)

#add lib:noprefix.a. if lib not contain lib prefix,
#it must be add : before like below
#same as libsample, you should build noprefix first after run cmake ..
TARGET_LINK_LIBRARIES(main :noprefix.a)
