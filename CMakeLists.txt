cmake_minimum_required(VERSION 3.0.0...3.24 FATAL_ERROR)
project(webgpu-backend-wgpu VERSION 1.0.0)

include("${CMAKE_CURRENT_LIST_DIR}/cmake/FetchWgpuBinary.cmake")

if (EMSCRIPTEN)

	target_include_directories(webgpu INTERFACE
		"${CMAKE_CURRENT_SOURCE_DIR}/include-emscripten"
	)

else (EMSCRIPTEN)

	target_include_directories(webgpu INTERFACE
		"${CMAKE_CURRENT_SOURCE_DIR}/include"
	)

endif (EMSCRIPTEN)
