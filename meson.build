project('libthpool', 'c', version: '0.1', default_options: ['warning_level=3'])

libthpool_include = ['thpool.h']
libthpool_sources = ['thpool.c']

libthpool = library(
    'libthpool',
    libthpool_sources,
    install: not meson.is_subproject(),
    version: meson.project_version(),
)

install_headers('thpool.h')

libthpool_dep = declare_dependency(
    link_with: libthpool,
    include_directories: '.',
)

subdir('tests')

pkg_mod = import('pkgconfig')
pkg_mod.generate(
    libthpool,
    name: 'libthpool',
    description: 'A library to access squashfs archives',
    libraries: libthpool,
    version: meson.project_version(),
)
