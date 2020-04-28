cmake_minimum_required(VERSION 3.10)

project(PicoSAT VERSION 965)

set(CMAKE_C_FLAGS "-DNALLSIGNALS -DNGETRUSAGE")

add_executable(picosat config.h picosat.h app.c main.c picosat.c version.c)