load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = ["example.go"],
    importpath = "github.com/docker/libnetwork/client/mflag/example",
    visibility = ["//visibility:private"],
    deps = ["//vendor/github.com/docker/libnetwork/client/mflag:go_default_library"],
)

go_binary(
    name = "example",
    importpath = "github.com/docker/libnetwork/client/mflag/example",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
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
