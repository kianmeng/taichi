# ./taichi/codegen/metal/CMakeLists.txt

add_library(metal_codegen)
target_sources(metal_codegen
  PRIVATE
    codegen_metal.cpp
    struct_metal.cpp
    env_config.cpp
  )

target_include_directories(metal_codegen
  PRIVATE
    ${PROJECT_SOURCE_DIR}
    ${PROJECT_SOURCE_DIR}/external/spdlog/include
    ${PROJECT_SOURCE_DIR}/external/eigen
    ${LLVM_INCLUDE_DIRS}
  )

target_link_libraries(metal_codegen PRIVATE metal_runtime)
