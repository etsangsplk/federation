load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "health.go",
        "setup.go",
    ],
    importpath = "github.com/miekg/coredns/middleware/health",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/mholt/caddy:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["health_test.go"],
    importpath = "github.com/miekg/coredns/middleware/health",
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
