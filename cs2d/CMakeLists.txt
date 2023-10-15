find_package(absl REQUIRED)
find_package(protobuf REQUIRED)

add_executable(cs2d
        main.cpp
)

set_target_properties(cs2d PROPERTIES POSITION_INDEPENDENT_CODE ON)
target_compile_features(cs2d PRIVATE cxx_std_20)
target_include_directories(cs2d PUBLIC include)
target_link_libraries(cs2d
        PRIVATE cs2pp
        PRIVATE cs2proto
        PRIVATE protobuf::protobuf
        PRIVATE abseil::abseil
)
