project(mausezahn)

cmake_minimum_required(VERSION 2.4.0 FATAL_ERROR)
if(COMMAND cmake_policy)
	cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

SET(CMAKE_C_FLAGS "-Wall -pipe -fexceptions -fstack-protector --param=ssp-buffer-size=4 -fasynchronous-unwind-tables")

ADD_CUSTOM_TARGET(uninstall
	COMMAND ${CMAKE_COMMAND} -E echo Use 'xargs rm < install_manifest.txt' to uninstall this program
	)

include_directories(./ ../ ${CMAKE_CURRENT_BINARY_DIR})

add_subdirectory (src)
add_subdirectory (doc)



