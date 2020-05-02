cmake_minimum_required(VERSION 3.10)

project(PicoSAT VERSION 965)

set(CompilerFlags "-DNALLSIGNALS -DNGETRUSAGE")

if(WIN32)
    set(CompilerFlags "${CompilerFlags} -DPLWIN")
endif()

set(CMAKE_C_FLAGS ${CompilerFlags})
set(CommonSources config.h picosat.h picosat.c version.c)

add_executable(picosat ${CommonSources} app.c main.c)

add_executable(picomus ${CommonSources} picomus.c)

add_executable(picomcs ${CommonSources} picomcs.c)

add_executable(picogcnf ${CommonSources} picogcnf.c)