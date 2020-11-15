cmake_minimum_required(VERSION 3.5)
PROJECT(cppjieba)
if (CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
    set (CMAKE_INSTALL_PREFIX "/usr/local/cppjieba" CACHE PATH "default install path" FORCE )
endif()

add_library(${PROJECT_NAME} INTERFACE)
add_library(sub::cppjieba ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    INTERFACE
      ${PROJECT_SOURCE_DIR}/include
      ${PROJECT_SOURCE_DIR}/deps
)

install(TARGETS ${PROJECT_NAME} LIBRARY DESTINATION lib) 
install(DIRECTORY ${PROJECT_SOURCE_DIR}/include DESTINATION include) 
# install(DIRECTORY ${PROJECT_SOURCE_DIR}/deps DESTINATION include) 



# CMAKE_MINIMUM_REQUIRED (VERSION 2.6)
# ADD_SUBDIRECTORY(deps)
# ADD_SUBDIRECTORY(test)


# INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/deps  ${PROJECT_SOURCE_DIR}/include)

# ADD_DEFINITIONS(-O3 -Wall -g)
# IF(APPLE) # mac os
    # ADD_DEFINITIONS(-std=c++0x)
# endif()

# cmake .. -DENC=GBK
# IF (DEFINED ENC)
#     ADD_DEFINITIONS(-DCPPJIEBA_${ENC})
# ENDIF()


# ENABLE_TESTING()
# ADD_TEST(NAME ./test/test.run COMMAND ./test/test.run)
# ADD_TEST(NAME ./load_test COMMAND ./load_test)
# ADD_TEST(NAME ./demo COMMAND ./demo)
