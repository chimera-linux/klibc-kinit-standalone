nfsmount_srcs = [
    'main.c',
    'mount.c',
    'portmap.c',
    'dummypmap.c',
    'sunrpc.c',
    'bindresvport.c',
]

nfsmount_lib = static_library('nfsmount_lib',
    nfsmount_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_root, include_directories('.')],
    install: false,
)

kinit_libs += [nfsmount_lib]

executable('nfsmount',
    ['main_standalone.c'],
    link_whole: [nfsmount_lib],
    install: true,
    install_dir: bin_path,
)

