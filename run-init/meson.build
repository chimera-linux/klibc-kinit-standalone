run_init_srcs = [
    'runinitlib.c',
]

run_init_lib = static_library('run_init_lib',
    run_init_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_root, include_directories('.')],
    install: false,
)

kinit_libs += [run_init_lib]

executable('run-init',
    'run-init.c',
    link_with: [klib],
    link_whole: [run_init_lib],
    install: true,
    install_dir: bin_path,
)

