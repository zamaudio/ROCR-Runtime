# Static map file
verfile = 'hsacore.so.def'
linkfile = 'hsacore.so.link'
vflag = '-Wl,--version-script,@0@/@1@'.format(meson.current_source_dir(), verfile)
lflag = '-Wl,@0@/@1@ '.format(meson.current_source_dir(), linkfile)

args = [ '-D__linux__',
	 '-DHSA_EXPORT=1',
	 '-DHSA_EXPORT_FINALIZER=1',
	 '-DHSA_EXPORT_IMAGES=1',
	 '-D HSA_DEPRECATED=',
]
add_global_arguments(args, language : 'cpp')

deps = dependency('libelf')
inc = include_directories(['.', 'inc'])

subdir('inc')
subdir('core')
subdir('loader')
subdir('libamdhsacode')

srcs = ['core/util/lnx/os_linux.cpp',
	'core/util/small_heap.cpp',
	'core/util/timer.cpp'
]

lwith = [ hsaloader, hsaruntime, amdhsacode ]

amdhsaruntime = shared_module('hsa-runtime',
  sources: srcs,
  link_args : [vflag, lflag],
  include_directories : inc,
  link_with : lwith,
  dependencies : deps,
  install : true)
