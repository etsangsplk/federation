load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "ebnf.go",
        "parser.go",
    ],
    importpath = "golang.org/x/exp/ebnf",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["ebnf_test.go"],
    importpath = "golang.org/x/exp/ebnf",
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
