executable(
  'tvg-svg2png',
  files('svg2png.cpp', 'lodepng.cpp'),
  dependencies : [thorvg_dep, dependency('threads')],
  cpp_args : ['-DFONT_DIR="@0@"'.format(font_dir)],
  install : true,
)
