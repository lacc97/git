project('git', 'c', version : '1.3.5')

if get_option('glk_backend') == 'glkterm'
    glk_dep = dependency('glkterm', static : true)
elif get_option('glk_backend') == 'glktermw'
    glk_dep = dependency('glktermw', static : true)
else
    error('Glk backend not specified via \'glk_backend\' option')
endif

math_dep = meson.get_compiler('c').find_library('m', required : false)

os_src='git_unix.c'

git_srcs = [
    'compiler.c',
    'gestalt.c',
    'git.c',
    'glkop.c',
    'heap.c',
    'memory.c',
    'opcodes.c',
    'operands.c',
    'peephole.c',
    'savefile.c',
    'saveundo.c',
    'search.c',
    'terp.c',
    'accel.c',
    os_src
]

executable('git', sources : git_srcs, dependencies : [glk_dep, math_dep], c_args : ['-DUSE_DIRECT_THREADING', '-DUSE_MMAP', '-DUSE_INLINE'], install : true)
 
 
