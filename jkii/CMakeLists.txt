CMAKE_MINIMUM_REQUIRED(VERSION 3.5)
PROJECT(jkii C)
SET(CMAKE_C_FLAGS "-Wall")

SET(CMAKE_C_FLAGS_RELEASE "-O2")
SET(CMAKE_C_FLAGS_DEBUG "-g")

FILE(GLOB srcs src/*.c libs/jsmn/*.c)
FILE(GLOB hdrs include/*.h libs/jsmn/jsmn.h)
ADD_LIBRARY(jkii SHARED ${srcs})
TARGET_INCLUDE_DIRECTORIES(jkii PUBLIC ./include)
TARGET_INCLUDE_DIRECTORIES(jkii PRIVATE ./libs/jsmn)
INSTALL(FILES ${hdrs} DESTINATION include)
INSTALL(TARGETS jkii DESTINATION lib)
