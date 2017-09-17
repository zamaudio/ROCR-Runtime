srcs = [ 'amd_elf_image.cpp',
	 'amd_hsa_code_util.cpp',
	 'amd_hsa_locks.cpp',
	 'amd_options.cpp',
	 'amd_hsa_code.cpp',
]

deps = dependency('libelf')

libamdhsacode = shared_library('amdhsacode',
  sources: srcs,
  include_directories : inc,
  dependencies : deps)
