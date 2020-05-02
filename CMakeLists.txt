cmake_minimum_required(VERSION 3.10)

project(PicoSAT VERSION 965)

set(CompilerFlags "-DNALLSIGNALS -DNGETRUSAGE")

option(Logging "More logging" OFF)
option(Trace "Trace support" OFF)
option(Stats "More stats" OFF)

if(CMAKE_BUILD_TYPE MATCHES Debug)
    message("Compiling in debug mode. For release mode, pass -DCMAKE_BUILD_TYPE=Release to CMake.")
    set(Logging ON)
    set(Trace ON)
    set(Stats ON)
endif()

if(WIN32)
    message("Compiling for Windows platform")
    set(CompilerFlags "${CompilerFlags} -DPLWIN")
endif()

if (Logging)
    message("Compiling with additional logging")
    set(CompilerFlags "${CompilerFlags} -DLOGGING")
endif()

if (Trace)
    message("Compiling with trace support")
    set(CompilerFlags "${CompilerFlags} -DTRACE")
endif()

if (Stats)
    message("Compiling with additional stats")
    set(CompilerFlags "${CompilerFlags} -DSTATS")
endif()

set(CMAKE_C_FLAGS ${CompilerFlags})
set(CommonSources config.h picosat.h picosat.c version.c)

add_executable(picosat ${CommonSources} app.c main.c)

add_executable(picomus ${CommonSources} picomus.c)

add_executable(picomcs ${CommonSources} picomcs.c)

add_executable(picogcnf ${CommonSources} picogcnf.c)