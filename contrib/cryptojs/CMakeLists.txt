FILE(GLOB_RECURSE cryptojs_SOURCES "*.cpp")

ADD_LIBRARY(cryptojs_static STATIC ${cryptojs_SOURCES})
SET_TARGET_PROPERTIES(cryptojs_static PROPERTIES OUTPUT_NAME cryptojs)
TARGET_LINK_LIBRARIES(cryptojs_static)
INSTALL(TARGETS cryptojs_static DESTINATION lib)

IF(ENABLE_SHARED_LIBS)
    ADD_LIBRARY(cryptojs_shared SHARED ${cryptojs_SOURCES})
    SET_TARGET_PROPERTIES(cryptojs_shared PROPERTIES OUTPUT_NAME cryptojs)
    TARGET_LINK_LIBRARIES(cryptojs_shared)
    INSTALL(TARGETS cryptojs_shared DESTINATION lib)
ENDIF()
