load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "encode.go",
        "hpack.go",
        "huffman.go",
        "tables.go",
    ],
    importpath = "golang.org/x/net/http2/hpack",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "encode_test.go",
        "hpack_test.go",
        "tables_test.go",
    ],
    importpath = "golang.org/x/net/http2/hpack",
    library = ":go_default_library",
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
