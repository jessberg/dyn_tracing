load("//bazel/wasm:wasm.bzl", "wasm_cc_binary")
load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library", "cc_test")

wasm_cc_binary(
    name = "filter.wasm",
    srcs = [
        "filter.cc",
    ],
    deps = [
        ":graph_utils",
        "@com_google_absl//absl/strings",
        "@envoy_wasm_api//:proxy_wasm_intrinsics",
    ],
)

cc_test(
    name = "filter_test",
    srcs = [
        "filter_test.cc",
    ],
    deps = [
        "@com_google_protobuf//:protobuf_lite",
        "@gtest",
        "@gtest//:gtest_main",
    ],
)

cc_test(
    name = "str_utils_test",
    srcs = [
        "str_utils_test.cc",
    ],
    deps = [
        "@com_google_absl//absl/strings",
        "@gtest",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "graph_utils",
    srcs = [
        "graph_utils.cc",
    ],
    hdrs = [
        "graph_utils.h",
    ],
    deps = [
        "@boost//:graph",
        "@com_google_absl//absl/strings",
    ],
)

cc_test(
    name = "graph_utils_test",
    srcs = [
        "graph_utils_test.cc",
    ],
    deps = [
        ":graph_utils",
        "@gtest",
        "@gtest//:gtest_main",
    ],
)

cc_binary(
    name = "dfs_example",
    srcs = [
        "dfs_example.cc",
    ],
    deps = [
        "@boost//:graph",
    ],
)
