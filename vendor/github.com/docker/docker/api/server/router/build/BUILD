load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "backend.go",
        "build.go",
        "build_routes.go",
    ],
    importpath = "github.com/docker/docker/api/server/router/build",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/docker/api/errors:go_default_library",
        "//vendor/github.com/docker/docker/api/server/httputils:go_default_library",
        "//vendor/github.com/docker/docker/api/server/router:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/backend:go_default_library",
        "//vendor/github.com/docker/docker/api/types/container:go_default_library",
        "//vendor/github.com/docker/docker/api/types/versions:go_default_library",
        "//vendor/github.com/docker/docker/pkg/ioutils:go_default_library",
        "//vendor/github.com/docker/docker/pkg/progress:go_default_library",
        "//vendor/github.com/docker/docker/pkg/streamformatter:go_default_library",
        "//vendor/github.com/docker/go-units:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
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
