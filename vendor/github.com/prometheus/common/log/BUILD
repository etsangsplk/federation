load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "log.go",
        "syslog_formatter.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "eventlog_formatter.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/prometheus/common/log",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/Sirupsen/logrus:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "//vendor/golang.org/x/sys/windows/svc/eventlog:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "log_test.go",
        "syslog_formatter_test.go",
    ],
    importpath = "github.com/prometheus/common/log",
    library = ":go_default_library",
    deps = ["//vendor/github.com/Sirupsen/logrus:go_default_library"],
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
