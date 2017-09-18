# Static map file
verfile = 'hsacore.so.def'
linkfile = 'hsacore.so.link'
vflag = '-Wl,--version-script,@0@/@1@'.format(meson.current_source_dir(), verfile)
lflag = '-Wl,@0@/@1@'.format(meson.current_source_dir(), linkfile)

args = [ '-D__linux__',
	 '-DHSA_EXPORT=1',
	 '-DHSA_EXPORT_FINALIZER=1',
	 '-DHSA_EXPORT_IMAGES=1',
	 '-D HSA_DEPRECATED=',
]
add_global_arguments(args, language : 'cpp')

inc = include_directories(['.', 'inc', 'core/inc', 'libamdhsacode'])

subdir('inc')
subdir('core')
#subdir('loader')
subdir('libamdhsacode')

srcs = [ 'loader/executable.cpp', 'loader/loaders.cpp' ]

#lwith = [ amdhsaloader, libamdhsacode, amdhsaruntime, amdhsautil ]
lwith = [ libamdhsacode, amdhsaruntime, amdhsautil ]

shared_module('hsa-runtime',
  sources: srcs, include_directories : inc,
#  link_args : [vflag, lflag],
  link_args : vflag,
  link_depends : [verfile, linkfile],
  link_with : lwith,
  install : true)
