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

add_library(unio_analyzer SHARED ${SOURCES})
target_link_libraries(unio_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS unio_analyzer RUNTIME DESTINATION ".")
else()
    install(TARGETS unio_analyzer LIBRARY DESTINATION ".")
endif()
