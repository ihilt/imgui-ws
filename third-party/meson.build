if 'IMGUI_WS_ALL_WARNINGS_3RD_PARTY'
  if 'CMAKE_COMPILER_IS_GNUCC', 'OR', 'CMAKE_CXX_COMPILER_ID', 'MATCHES', 'Clang'
    cmake_cxx_flags = '${CMAKE_CXX_FLAGS} -Wall -Wextra -pedantic'
  else
    # todo : windows
  endif
endif
if 'APPLE'
  additional_libraries = '-framework Cocoa'
else
  # unset('ADDITIONAL_LIBRARIES')
endif
imgui_lib = shared_library('imgui', 'imgui/imgui/imgui.cpp', 'imgui/imgui/imgui_draw.cpp', 'imgui/imgui/imgui_demo.cpp', 'imgui/imgui/imgui_widgets.cpp', 'imgui/imgui/imgui_tables.cpp')
# target_include_directories(['imgui', 'INTERFACE', 'imgui'])
# target_include_directories(['imgui', 'PRIVATE', 'imgui/imgui'])
# target_link_libraries(['imgui', 'PRIVATE', additional_libraries])
if 'IMGUI_WS_SUPPORT_SDL2'
  OpenGL_dep = dependency('OpenGL')
  SDL2_dep = dependency('SDL2')
  # string(['STRIP', '${SDL2_LIBRARIES}', 'SDL2_LIBRARIES'])
  imgui-sdl2_lib = shared_library('imgui-sdl2', 'imgui/imgui/examples/libs/gl3w/GL/gl3w.c', 'imgui/imgui/examples/imgui_impl_sdl.cpp', 'imgui/imgui/examples/imgui_impl_opengl3.cpp')
  # target_include_directories(['imgui-sdl2', 'PUBLIC', 'imgui/imgui/examples/libs/gl3w', sdl2_include_dirs])
  # target_include_directories(['imgui-sdl2', 'PRIVATE', 'imgui/imgui', 'imgui/imgui/examples'])
  # target_link_libraries(['imgui-sdl2', 'PUBLIC', sdl2_libraries])
  # target_link_libraries(['imgui-sdl2', 'PRIVATE', 'imgui', opengl_libraries, cmake_dl_libs, cmake_thread_libs_init, additional_libraries])
endif
subdir('incppect')
