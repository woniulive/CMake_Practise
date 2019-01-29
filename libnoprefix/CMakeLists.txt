
SET(LIBNOPREFIX libnoprefix.c)

ADD_LIBRARY(noprefix STATIC ${LIBNOPREFIX})

#override prefix lib to none,so this out will be noprefix.a
SET_TARGET_PROPERTIES(noprefix PROPERTIES PREFIX "")

SET(LIBRARY_OUTPUT_PATH libnoprefix)

