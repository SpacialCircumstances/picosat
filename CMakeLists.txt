cmake_minimum_required(VERSION 3.10)

file(GLOB SOURCES
        *.h
        *.c)


project(PicoSAT VERSION 965)

set(CMAKE_C_FLAGS "-DNALLSIGNALS -DNGETRUSAGE")

add_executable(picosat ${SOURCES})