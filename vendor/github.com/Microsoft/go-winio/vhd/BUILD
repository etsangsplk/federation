load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "zvhd.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "vhd.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/Microsoft/go-winio/vhd",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/sys/windows:go_default_library"],
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
