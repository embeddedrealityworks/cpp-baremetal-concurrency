project(
    'baremetal-concurrency',
    'cpp',
    version: '0.1.0',
    license: 'MIT',
    meson_version: '>=1.1.0',
    default_options: [
        'cpp_std=c++23',
    ],
)

inc = include_directories('include')

concurrency_compile_args = []
if get_option('simulate_freestanding')
    concurrency_compile_args += '-DSIMULATE_FREESTANDING'
endif

concurrency_dep = declare_dependency(
    include_directories: inc,
    compile_args: concurrency_compile_args,
)

install_headers(
    'include/conc/atomic.hpp',
    'include/conc/concepts.hpp',
    'include/conc/concurrency.hpp',
    subdir: 'conc',
)

install_headers(
    'include/conc/detail/freestanding.hpp',
    subdir: 'conc/detail',
)
