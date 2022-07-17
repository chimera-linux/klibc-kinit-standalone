project('klibc-kinit-standalone', ['c'],
    version: '2.0.10',
    default_options: ['c_std=gnu99', 'warning_level=2', 'buildtype=plain'],
    license: 'MIT',
)

zlib = dependency('zlib', required: true)

common_cargs = [
    '-D_DEFAULT_SOURCE',
    '-DCONFIG_KLIBC_ZLIB',
]

klib_srcs = [
    'name_to_dev.c',
    'devname.c',
    'getarg.c',
    'capabilities.c',
]

kinit_srcs = [
    'kinit.c',
    'do_mounts.c',
    'do_mounts_md.c',
    'do_mounts_mtd.c',
    'getintfile.c',
    'initrd.c',
    'nfsroot.c',
    'ramdisk_load.c',
    'readfile.c',
    'xpio.c',
]

inc_root = include_directories('.')

inc_all = include_directories(
    '.', 'fstype', 'ipconfig', 'nfsmount', 'resume', 'run-init'
)

klib = static_library('klib',
    klib_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_all],
    install: false,
)

kinit_libs = [klib]

bin_path = join_paths(get_option('libexecdir'), 'kinit-standalone')

subdir('fstype')
subdir('ipconfig')
subdir('nfsmount')
subdir('resume')
subdir('run-init')

executable('kinit',
    kinit_srcs,
    c_args: common_cargs,
    include_directories: [inc_all],
    dependencies: [zlib],
    link_whole: kinit_libs,
    install: true,
    install_dir: bin_path,
)

