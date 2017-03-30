cxx_library(
  name = 'blake',
  header_namespace = 'blake',
  exported_headers = subdir_glob([
    ('Source/C++11/blake', '*.h'),
  ]),
  srcs = glob([
    'Source/C++11/blake/*.cpp',
  ]),
)

cxx_library(
  name = 'equihash',
  header_namespace = 'equihash',
  exported_headers = {
    'pow.h': 'Source/C++11/pow.h',
  },
  srcs = [
    'Source/C++11/pow.cc',
  ],
  compiler_flags = [
    '-std=c++11',
  ],
  deps = [
    ':blake',
  ],
)

cxx_binary(
  name = 'pow-test',
  srcs = [
    'Source/C++11/pow-test.cc',
  ],
  compiler_flags = [
    '-std=c++11',
  ],
  deps = [
    ':equihash',
  ],
)
