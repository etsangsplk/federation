load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "common.go",
        "reader.go",
        "writer.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "stat_atimespec.go",
            "stat_unix.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "stat_atim.go",
            "stat_unix.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/Microsoft/go-winio/archive/tar",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "reader_test.go",
        "tar_test.go",
        "writer_test.go",
    ],
    data = glob(["testdata/**"]),
    importpath = "github.com/Microsoft/go-winio/archive/tar",
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = ["example_test.go"],
    data = glob(["testdata/**"]),
    importpath = "github.com/Microsoft/go-winio/archive/tar_test",
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
