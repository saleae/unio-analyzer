cmake_minimum_required (VERSION 3.11)
project(unio_analyzer)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/UnioAnalyzer.cpp
src/UnioAnalyzer.h
src/UnioAnalyzerResults.cpp
src/UnioAnalyzerResults.h
src/UnioAnalyzerSettings.cpp
src/UnioAnalyzerSettings.h
src/UnioSimulationDataGenerator.cpp
src/UnioSimulationDataGenerator.h
)

add_analyzer_plugin(unio_analyzer SOURCES ${SOURCES})
