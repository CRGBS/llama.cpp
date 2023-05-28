#
# starcoder-quantize

set(TARGET quantize)
add_executable(${TARGET} quantize.cpp)
target_link_libraries(${TARGET} PRIVATE ggml common common-ggml llama ${CMAKE_THREAD_LIBS_INIT})
target_compile_features(${TARGET} PRIVATE cxx_std_20)
if(TARGET BUILD_INFO)
  add_dependencies(${TARGET} BUILD_INFO)
endif()
