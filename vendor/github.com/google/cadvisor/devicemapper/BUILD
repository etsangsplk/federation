load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "dmsetup_client.go",
        "doc.go",
        "thin_ls_client.go",
        "thin_pool_watcher.go",
        "util.go",
    ],
    importpath = "github.com/google/cadvisor/devicemapper",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/golang/glog:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "thin_ls_client_test.go",
        "thin_pool_watcher_test.go",
    ],
    importpath = "github.com/google/cadvisor/devicemapper",
    library = ":go_default_library",
    deps = ["//vendor/github.com/google/cadvisor/devicemapper/fake:go_default_library"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/google/cadvisor/devicemapper/fake:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
