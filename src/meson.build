font_dir = get_option('prefix') / get_option('datadir') / 'thorvg-cli-tools/fonts'

install_data(
  meson.project_source_root() / 'fonts/PublicSans-Regular.ttf',
  meson.project_source_root() / 'fonts/LICENSE.md',
  install_dir : font_dir,
)

if 'all' in enabled_tools or 'svg2png' in enabled_tools
  subdir('svg2png')
endif

if 'all' in enabled_tools or 'lottie2gif' in enabled_tools
  subdir('lottie2gif')
endif
