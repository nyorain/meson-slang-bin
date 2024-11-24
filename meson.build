project('slang', ['cpp', 'c'],
	meson_version: '>=0.51',
	default_options: [
		'cpp_std=c++11',
		'c_std=c11',
  		'warning_level=3',
  		'werror=false'])

cc = meson.get_compiler('cpp')

inc_slang = include_directories('include')

lib_slang = disabler()

if build_machine.system() == 'linux'
	lib_slang = cc.find_library('slang', dirs:
		meson.current_source_dir() + '/lib/linux')
elif build_machine.system() == 'windows'
	lib_slang = cc.find_library('slang', dirs:
		meson.current_source_dir() + '/lib/win64')
endif

dep_slang = declare_dependency(
	dependencies: [lib_slang],
	include_directories: inc_slang)

