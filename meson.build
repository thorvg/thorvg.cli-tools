project('thorvg-cli-tools',
        'cpp',
        default_options : ['buildtype=debugoptimized', 'b_sanitize=none', 'werror=false', 'optimization=3', 'cpp_std=c++14'],
        license : 'MIT')

thorvg_dep = dependency('thorvg-1', required : false)
if not thorvg_dep.found()
  thorvg_dep = dependency('thorvg')
endif

enabled_tools = get_option('tools')

subdir('src')

summary(
  {
    'ThorVG' : thorvg_dep.version(),
    'Tools' : enabled_tools,
  },
  section : 'Build configuration',
  bool_yn : true,
)
