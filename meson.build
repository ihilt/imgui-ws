project('imgui-ws', 'cpp', 'c')
cm_imgui_ws_inc = include_directories(
  'include',
  'third-party/imgui',
  'third-party/incppect/third_party/uWebSockets/src',
  'third-party/incppect/third_party/uWebSockets/uSockets/src',
  'third-party/incppect/include',
)
cm_imgui_ws_src = files(
  'third-party/incppect/third_party/uWebSockets/uSockets/src/context.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/loop.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/socket.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/ssl.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/eventing/epoll_kqueue.c',
  'third-party/incppect/third_party/uWebSockets/uSockets/src/eventing/gcd.c',
  'third-party/incppect/src/incppect.cpp',
  'src/imgui-ws.cpp',
  'src/compressor-xor-rle-per-draw-list.cpp',
  'src/compressor-xor-rle-per-draw-list-with-vtx-offset.cpp',
)
threads_dep = dependency('threads')
cm_imgui_ws = library(
  'cm_imgui_ws',
  cm_imgui_ws_src,
  include_directories : cm_imgui_ws_inc,
  c_args : ['-DNDEBUG', '-DINCPPECT_NO_SSL=1', '-DLIBUS_NO_SSL=1', '-DUWS_NO_ZLIB'],
  cpp_args : ['-DNDEBUG', '-DINCPPECT_NO_SSL=1', '-DLIBUS_NO_SSL=1', '-DUWS_NO_ZLIB'],
  dependencies: threads_dep
)
cm_imgui_ws_dep = declare_dependency(
  link_with : cm_imgui_ws,
  include_directories : cm_imgui_ws_inc,
  dependencies: threads_dep
)
