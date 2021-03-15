if 'IMGUI_WS_ALL_WARNINGS'
  if 'CMAKE_COMPILER_IS_GNUCC', 'OR', 'CMAKE_CXX_COMPILER_ID', 'MATCHES', 'Clang'
    cmake_cxx_flags = '${CMAKE_CXX_FLAGS} -Wall -Wextra -pedantic'
  else
    # todo : windows
  endif
endif
# file(['READ', 'imgui-ws.js', 'src_imgui-ws_js'])
# configure_file([cmake_current_source_dir, '/common.h.in', cmake_current_source_dir, '/common.h', '@ONLY'])
imgui-ws_lib = library('imgui-ws', imtui_library_type, 'imgui-ws.cpp', 'compressor-xor-rle-per-draw-list.cpp', 'compressor-xor-rle-per-draw-list-with-vtx-offset.cpp')
# target_include_directories(['imgui-ws', 'PUBLIC', '../include'])
# target_link_libraries(['imgui-ws', 'PRIVATE', 'imgui', 'incppect', cmake_dl_libs, cmake_thread_libs_init])
