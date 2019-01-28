#change libsample to another name
SET(LIBSAMPLE libsample.c)

#create a shared lib named sample(cmake will change it to libsample.so)
ADD_LIBRARY(sample SHARED ${LIBSAMPLE})

#create a static lib named sample_static(cmake will change it to libsample_static.a)
ADD_LIBRARY(sample_static STATIC ${LIBSAMPLE})

#since ADD_LIBRARY(sample SHARED ${LIBSAMPLE}) & 
#ADD_LIBRARY(sample STATIC ${LIBSAMPLE}) can not use meanwhile,
#because of name conflict, we use SET_TARGET_PROPERTIES
SET_TARGET_PROPERTIES(sample_static PROPERTIES OUTPUT_NAME "sample")

#we can use GET_TARGET_PROPERTY to get value set by SET_TARGET_PROPERTIES
#it will NOTFOUND if this property is not defined before
GET_TARGET_PROPERTY(OUTPUT_VALUE sample_static OUTPUT_NAME)
GET_TARGET_PROPERTY(NOT_EXIST_VALUE sample_static INPUT_NAME)
MESSAGE(STATUS "This is the sample_static OUTPUT_NAME:" ${OUTPUT_VALUE})
MESSAGE(STATUS "This is NOT_EXIST_VALUE:" ${NOT_EXIST_VALUE})

#change cmake output library file to ./lib(. means folder you run command)
SET(LIBRARY_OUTPUT_PATH lib)

