load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["grpclb_server_generated.go"],
    importpath = "google.golang.org/grpc/grpclb",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/google.golang.org/grpc:go_default_library",
        "//vendor/google.golang.org/grpc/grpclb/grpc_lb_v1:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["grpclb_test.go"],
    importpath = "google.golang.org/grpc/grpclb",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
        "//vendor/google.golang.org/grpc/codes:go_default_library",
        "//vendor/google.golang.org/grpc/credentials:go_default_library",
        "//vendor/google.golang.org/grpc/grpclb/grpc_lb_v1:go_default_library",
        "//vendor/google.golang.org/grpc/metadata:go_default_library",
        "//vendor/google.golang.org/grpc/naming:go_default_library",
        "//vendor/google.golang.org/grpc/test/grpc_testing:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//vendor/google.golang.org/grpc/grpclb/grpc_lb_v1:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
