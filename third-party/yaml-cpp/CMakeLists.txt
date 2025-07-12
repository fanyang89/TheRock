therock_subproject_fetch(therock-yaml-cpp-sources
  CMAKE_PROJECT
  # Originally mirrored from: https://github.com/jbeder/yaml-cpp/archive/refs/tags/0.8.0.tar.gz
  URL /home/fanmi/workspace/OpenBLAS/yaml-cpp-0.8.0-patched.tar.gz
  URL_HASH SHA256=55b91e014d2fee4f5d8774b0ee445c32369ba495e66db379bb395e3bcc637475
)

therock_cmake_subproject_declare(therock-yaml-cpp
  BACKGROUND_BUILD
  EXCLUDE_FROM_ALL
  NO_MERGE_COMPILE_COMMANDS
  OUTPUT_ON_FAILURE
  EXTERNAL_SOURCE_DIR "${CMAKE_CURRENT_BINARY_DIR}/source"
  BUILD_DEPS
    therock-fmt
  CMAKE_ARGS
    -DYAML_BUILD_SHARED_LIBS=OFF
)
therock_cmake_subproject_provide_package(therock-yaml-cpp yaml-cpp lib/cmake)
therock_cmake_subproject_activate(therock-yaml-cpp)

add_dependencies(therock-third-party therock-yaml-cpp)
