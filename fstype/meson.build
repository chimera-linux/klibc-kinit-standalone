fstype_srcs = [
    'fstype.c',
]

fstype_lib = static_library('fstype_lib',
    fstype_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_root, include_directories('.')],
    install: false,
)

kinit_libs += [fstype_lib]

executable('fstype',
    'main.c',
    link_whole: [fstype_lib],
    install: true,
    install_dir: bin_path,
)

