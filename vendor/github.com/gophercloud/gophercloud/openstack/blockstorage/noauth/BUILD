load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "requests.go",
    ],
    importpath = "github.com/gophercloud/gophercloud/openstack/blockstorage/noauth",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/gophercloud/gophercloud:go_default_library"],
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
        "//vendor/github.com/gophercloud/gophercloud/openstack/blockstorage/noauth/testing:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
