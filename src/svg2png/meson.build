font_dir = get_option('prefix') / get_option('datadir') / 'thorvg-cli-tools/fonts'

install_data(meson.project_source_root() / 'fonts/PublicSans-Regular.ttf', install_dir : font_dir)

executable(
  'tvg-svg2png',
  files('svg2png.cpp', 'lodepng.cpp'),
  dependencies : [thorvg_dep, dependency('threads')],
  cpp_args : ['-DFONT_DIR="@0@"'.format(font_dir)],
  install : true,
)
