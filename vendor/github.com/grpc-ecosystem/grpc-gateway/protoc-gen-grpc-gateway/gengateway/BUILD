load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "generator.go",
        "template.go",
    ],
    importpath = "github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/gengateway",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/golang/protobuf/protoc-gen-go/plugin:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/descriptor:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/generator:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/utilities:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["template_test.go"],
    importpath = "github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/gengateway",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/golang/protobuf/protoc-gen-go/descriptor:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/descriptor:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway/httprule:go_default_library",
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
