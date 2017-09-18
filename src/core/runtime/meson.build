srcs = [ 'amd_blit_kernel.cpp'
	,'amd_blit_sdma.cpp'
	,'amd_cpu_agent.cpp'
	,'amd_gpu_agent.cpp'
	,'amd_aql_queue.cpp'
	,'amd_loader_context.cpp'
	,'hsa_ven_amd_loader.cpp'
	,'amd_memory_region.cpp'
	,'amd_topology.cpp'
	,'default_signal.cpp'
	,'host_queue.cpp'
	,'hsa.cpp'
	,'hsa_api_trace.cpp'
	,'hsa_ext_amd.cpp'
	,'hsa_ext_interface.cpp'
	,'interrupt_signal.cpp'
	,'isa.cpp'
	,'runtime.cpp'
	,'signal.cpp'
	,'queue.cpp'
	,'cache.cpp'
]

amdhsaruntime = shared_module('amdhsaruntime',
  sources: srcs,
  include_directories : inc)
