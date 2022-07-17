ipconfig_srcs = [
    'dhcp_proto.c',
    'bootp_proto.c',
    'main.c',
    'netdev.c',
    'packet.c',
]

ipconfig_lib = static_library('ipconfig_lib',
    ipconfig_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_root, include_directories('.')],
    install: false,
)

kinit_libs += [ipconfig_lib]

executable('ipconfig',
    [],
    link_whole: [ipconfig_lib],
    install: true,
    install_dir: bin_path,
)

