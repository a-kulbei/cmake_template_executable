FILE (GLOB_RECURSE project_SRCS *.cpp *.cxx *.cc *.C *.c *.h *.hpp)

SET (project_LIBS ${Boost_LIBRARIES})

SET (project_BIN ${PROJECT_NAME})

# we have a console app
ADD_EXECUTABLE(${project_BIN} ${project_SRCS})

##################################################################################################
# in case you have gui
##################################################################################################
# if (APPLE)
#	ADD_EXECUTABLE(${project_BIN} MACOSX_BUNDLE ${project_SRCS})
# elseif (WIN32)
#     ADD_EXECUTABLE(${project_BIN} WIN32 ${project_SRCS})
# elseif()
#	ADD_EXECUTABLE(${project_BIN} ${project_SRCS})
# endif()
##################################################################################################


TARGET_LINK_LIBRARIES(${project_BIN} ${project_LIBS})


##################################################################################################
# In case you need boost
##################################################################################################
#  link to rt, to be able to link with Boost staticaly
#if(UNIX AND NOT APPLE)
#   TARGET_LINK_LIBRARIES(${project_BIN} rt)
#endif()