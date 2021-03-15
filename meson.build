project('imgui-ws', default_options : ['default_library=static'])
cmake_export_compile_commands = 'on'
cmake_runtime_output_directory = [cmake_binary_dir, '/bin']
if 'CMAKE_SOURCE_DIR', 'STREQUAL', 'CMAKE_CURRENT_SOURCE_DIR'
  imgui_ws_standalone = 'ON'
else
  imgui_ws_standalone = 'OFF'
endif
# options
# sanitizers
if 'IMGUI_WS_SANITIZE_THREAD'
  cmake_c_flags = '${CMAKE_C_FLAGS} -fsanitize=thread'
  cmake_cxx_flags = '${CMAKE_CXX_FLAGS} -fsanitize=thread'
endif
if 'IMGUI_WS_SANITIZE_ADDRESS'
  cmake_c_flags = '${CMAKE_C_FLAGS} -fsanitize=address -fno-omit-frame-pointer'
  cmake_cxx_flags = '${CMAKE_CXX_FLAGS} -fsanitize=address -fno-omit-frame-pointer'
endif
if 'IMGUI_WS_SANITIZE_UNDEFINED'
  cmake_c_flags = '${CMAKE_C_FLAGS} -fsanitize=undefined'
  cmake_cxx_flags = '${CMAKE_CXX_FLAGS} -fsanitize=undefined'
endif
# main
Threads_dep = dependency('Threads')
cmake_cxx_standard = '17'
cmake_cxx_standard_required = 'ON'
if 'NOT', 'CMAKE_BUILD_TYPE', 'AND', 'NOT', 'CMAKE_CONFIGURATION_TYPES'
  cmake_build_type = ['Release', 'CACHE', 'STRING', 'Build type', 'FORCE']
  # set_property(['CACHE', 'CMAKE_BUILD_TYPE', 'PROPERTY', 'STRINGS', 'Debug', 'Release', 'RelWithDebInfo'])
endif
subdir('third-party')
subdir('src')
if 'IMGUI_WS_STANDALONE'
  subdir('examples')
  subdir('tools')
endif
