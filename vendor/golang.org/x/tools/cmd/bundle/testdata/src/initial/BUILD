load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "a.go",
        "b.go",
        "c.go",
    ],
    importpath = "golang.org/x/tools/cmd/bundle/testdata/src/initial",
    visibility = ["//visibility:public"],
    deps = ["//vendor/domain.name/importdecl:go_default_library"],
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
