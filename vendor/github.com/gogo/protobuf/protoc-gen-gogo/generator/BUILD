load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "generator.go",
        "helper.go",
    ],
    importpath = "github.com/gogo/protobuf/protoc-gen-gogo/generator",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/protoc-gen-gogo/descriptor:go_default_library",
        "//vendor/github.com/gogo/protobuf/protoc-gen-gogo/plugin:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["name_test.go"],
    importpath = "github.com/gogo/protobuf/protoc-gen-gogo/generator",
    library = ":go_default_library",
    deps = ["//vendor/github.com/gogo/protobuf/protoc-gen-gogo/descriptor:go_default_library"],
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
