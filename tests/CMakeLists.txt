file(GLOB sources "*.hpp" "*.cpp")
set(formatted ${formatted} ${sources} PARENT_SCOPE)
add_executable(tests ${sources})
target_link_libraries(tests ${Boost_LIBRARIES} ${CONAN_LIBS})
if(UNIX)
	target_link_libraries(tests pthread rt)
endif()
