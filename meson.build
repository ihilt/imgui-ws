project('imgui-ws', 'cpp', 'c')
cm_imgui_dir = include_directories('third-party/imgui/imgui', '.')
cm_imgui_sys = include_directories(is_system : true)
cm_imgui_inc = [cm_imgui_dir, cm_imgui_sys]
cm_imgui_src = files('third-party/imgui/imgui/imgui.cpp', 'third-party/imgui/imgui/imgui_draw.cpp', 'third-party/imgui/imgui/imgui_demo.cpp', 'third-party/imgui/imgui/imgui_widgets.cpp')
cm_imgui = shared_library(
  'cm_imgui',
  [cm_imgui_src],
  build_by_default : false,
  link_args : [],
  link_with : [],
  include_directories : cm_imgui_inc,
  install : false,
  override_options : ['cpp_std=gnu++17'],
  objects : [],
  cpp_args : ['-O3', '-DNDEBUG', '-Dimgui_EXPORTS']
)
cm_imgui_dep = declare_dependency(
  link_args : [],
  link_with : cm_imgui,
  compile_args : [],
  include_directories : cm_imgui_inc
)
cm_uWS_dir = include_directories('third-party/incppect/third_party/uWebSockets/uSockets/src', '.')
cm_uWS_sys = include_directories(is_system : true)
cm_uWS_inc = [cm_uWS_dir, cm_uWS_sys]
cm_uWS_src = files(
  'third-party/incppect/third_party/uWebSockets/uSockets/src/context.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/loop.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/socket.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/ssl.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/eventing/epoll_kqueue.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/eventing/gcd.c'
)
cm_uWS = shared_library(
  'cm_uWS',
  [cm_uWS_src],
  build_by_default : false,
  link_args : [
      '-lpthread'
  ],
  link_with : [],
  include_directories : cm_uWS_inc,
  install : false,
  override_options : [],
  objects : [],
  c_args : ['-O3', '-DNDEBUG', '-DuWS_EXPORTS', '-DLIBUS_NO_SSL=1', '-DUWS_NO_ZLIB']
)
cm_uWS_dep = declare_dependency(
  link_args : [
      '-lpthread'
  ],
  link_with : cm_uWS,
  compile_args : ['-DUWS_NO_ZLIB'],
  include_directories : cm_uWS_inc
)
cm_incppect_dir = include_directories(
  'third-party/incppect/include',
  'third-party/incppect/src',
  'third-party/incppect/third_party/uWebSockets/uSockets/src',
  'third-party/incppect/third_party/uWebSockets/src',
  '.'
)
cm_incppect_sys = include_directories(is_system : true)
cm_incppect_inc = [cm_incppect_dir, cm_incppect_sys]
cm_incppect_src = files('third-party/incppect/src/incppect.cpp')
cm_incppect = shared_library(
  'cm_incppect',
  [cm_incppect_src],
  build_by_default : false,
  link_args : [
      '-lpthread'
  ],
  link_with : [cm_uWS],
  include_directories : cm_incppect_inc,
  install : false,
  override_options : ['cpp_std=gnu++17'],
  objects : [],
  cpp_args : ['-O3', '-DNDEBUG', '-DINCPPECT_DEBUG=1', '-Dincppect_EXPORTS', '-DINCPPECT_NO_SSL=1', '-DUWS_NO_ZLIB']
)
cm_incppect_dep = declare_dependency(
  link_args : [
      '-lpthread'
  ],
  link_with : cm_incppect,
  compile_args : [],
  include_directories : cm_incppect_inc
)
cm_imgui_ws_dir = include_directories('include', 'third-party/imgui', 'third-party/incppect/include', '.')
cm_imgui_ws_sys = include_directories(is_system : true)
cm_imgui_ws_inc = [cm_imgui_ws_dir, cm_imgui_ws_sys]
cm_imgui_ws_src = files('src/imgui-ws.cpp', 'src/compressor-xor-rle-per-draw-list.cpp', 'src/compressor-xor-rle-per-draw-list-with-vtx-offset.cpp')
cm_imgui_ws = shared_library(
  'cm_imgui_ws',
  [cm_imgui_ws_src],
  build_by_default : false,
  link_args : [
    '-ldl',
    '-lpthread',
  ],
  link_with : [cm_imgui, cm_incppect],
  include_directories : cm_imgui_ws_inc,
  install : false,
  override_options : ['cpp_std=gnu++17'],
  objects : [],
  cpp_args : ['-O3', '-DNDEBUG', '-Dimgui_ws_EXPORTS']
)
cm_imgui_ws_dep = declare_dependency(
  link_args : [
    '-ldl',
    '-lpthread',
  ],
  link_with : cm_imgui_ws,
  compile_args : [],
  include_directories : cm_imgui_ws_inc
)
