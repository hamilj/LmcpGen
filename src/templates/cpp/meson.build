srcs_lmcp = [
  'avtas/lmcp/ByteBuffer.cpp',
  'avtas/lmcp/Factory.cpp',
  'avtas/lmcp/Node.cpp',
  'avtas/lmcp/NodeUtil.cpp',
  'avtas/lmcp/XMLParser.cpp',
  -<meson_source_list>-]

cpp = meson.get_compiler('cpp')

# mark as system header to disable all warnings when included
if cpp.get_id() == 'msvc'
  incs_lmcp = include_directories('.')
else
  incs_lmcp = include_directories('.', is_system : true)
endif

cpp_args_lmcp = []

if cpp.get_id() != 'msvc'
  cpp_args_lmcp += [
    '-std=c++11',
    '-Wall',
  ]
endif

lib_lmcp = static_library(
  'lmcp',
  srcs_lmcp,
  cpp_args: cpp_args_lmcp,
  include_directories: incs_lmcp,
)
