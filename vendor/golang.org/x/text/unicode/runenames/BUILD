load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "bits.go",
        "runenames.go",
        "tables.go",
    ],
    importpath = "golang.org/x/text/unicode/runenames",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["runenames_test.go"],
    importpath = "golang.org/x/text/unicode/runenames",
    library = ":go_default_library",
    deps = [
        "//vendor/golang.org/x/text/internal/gen:go_default_library",
        "//vendor/golang.org/x/text/internal/testtext:go_default_library",
        "//vendor/golang.org/x/text/internal/ucd:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = ["example_test.go"],
    importpath = "golang.org/x/text/unicode/runenames_test",
    deps = [":go_default_library"],
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
