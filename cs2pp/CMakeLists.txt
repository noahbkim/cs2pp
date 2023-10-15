find_package(absl REQUIRED)
find_package(protobuf REQUIRED)

include_directories(${proto_INCLUDE_DIRS})

add_library(cs2pp STATIC
        src/cs2pp.cpp
)

set_target_properties(cs2pp PROPERTIES POSITION_INDEPENDENT_CODE ON)
target_compile_features(cs2pp PRIVATE cxx_std_20)
target_include_directories(cs2pp PUBLIC include)
target_link_libraries(cs2pp
        PUBLIC cs2proto
        PUBLIC protobuf::protobuf  # Public API requires protobuf
        PRIVATE abseil::abseil
)
