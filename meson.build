project(
  'zlib',
  'c',
  version: '1.3.2',
  license: 'Zlib',
  meson_version: '>= 1.0.0',
  default_options: [
    'c_std=c99',
    'warning_level=1',
    'default_library=static',
  ],
)

zlib_sources = files(
  'src/adler32.c',
  'src/compress.c',
  'src/crc32.c',
  'src/deflate.c',
  'src/gzclose.c',
  'src/gzlib.c',
  'src/gzread.c',
  'src/gzwrite.c',
  'src/infback.c',
  'src/inffast.c',
  'src/inflate.c',
  'src/inftrees.c',
  'src/trees.c',
  'src/uncompr.c',
  'src/zutil.c',
)

zlib_internal_inc = include_directories('src', 'include/zlib')
zlib_public_inc = include_directories('include', is_system: true)

zlib_lib = static_library(
  'z',
  zlib_sources,
  include_directories: zlib_internal_inc,
)

zlib_dep = declare_dependency(
  link_with: zlib_lib,
  include_directories: zlib_public_inc,
)

meson.override_dependency('zlib', zlib_dep)
