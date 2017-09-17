srcs = [ 'amd_elf_image.cpp',
	 'amd_hsa_code_util.cpp',
	 'amd_hsa_locks.cpp',
	 'amd_options.cpp',
	 'amd_hsa_code.cpp',
]

amdhsacode = shared_library('amdhsacode',
  sources: srcs, link_args : lflag,
  include_directories : inc,
  dependencies : deps)
