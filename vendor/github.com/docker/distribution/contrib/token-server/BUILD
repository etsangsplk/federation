load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "errors.go",
        "main.go",
        "token.go",
    ],
    importpath = "github.com/docker/distribution/contrib/token-server",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/github.com/docker/distribution/context:go_default_library",
        "//vendor/github.com/docker/distribution/registry/api/errcode:go_default_library",
        "//vendor/github.com/docker/distribution/registry/auth:go_default_library",
        "//vendor/github.com/docker/distribution/registry/auth/htpasswd:go_default_library",
        "//vendor/github.com/docker/distribution/registry/auth/token:go_default_library",
        "//vendor/github.com/docker/libtrust:go_default_library",
        "//vendor/github.com/gorilla/mux:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
    ],
)

go_binary(
    name = "token-server",
    importpath = "github.com/docker/distribution/contrib/token-server",
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
