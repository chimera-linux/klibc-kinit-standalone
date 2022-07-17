resume_srcs = [
    'resumelib.c',
]

resume_lib = static_library('resume_lib',
    resume_srcs,
    c_args: common_cargs,
    pic: true,
    include_directories: [inc_root, include_directories('.')],
    install: false,
)

kinit_libs += [resume_lib]

executable('resume',
    'resume.c',
    link_with: [klib],
    link_whole: [resume_lib],
    install: true,
    install_dir: bin_path,
)

