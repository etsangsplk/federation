load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

filegroup(
    name = "go_default_library_protos",
    srcs = ["unrecognizedgroup.proto"],
    visibility = ["//visibility:public"],
)

go_library(
    name = "go_default_library",
    srcs = ["unrecognizedgroup.pb.go"],
    importpath = "github.com/gogo/protobuf/test/unrecognizedgroup",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/protoc-gen-gogo/descriptor:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "oldnew_test.go",
        "unrecognizedgrouppb_test.go",
    ],
    importpath = "github.com/gogo/protobuf/test/unrecognizedgroup",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/jsonpb:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
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
