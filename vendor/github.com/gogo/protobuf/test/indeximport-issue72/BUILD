load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

filegroup(
    name = "go_default_library_protos",
    srcs = ["indeximport.proto"],
    visibility = ["//visibility:public"],
)

go_library(
    name = "go_default_library",
    srcs = ["indeximport.pb.go"],
    importpath = "github.com/gogo/protobuf/test/indeximport-issue72",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/test/indeximport-issue72/index:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["indeximportpb_test.go"],
    importpath = "github.com/gogo/protobuf/test/indeximport-issue72",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/jsonpb:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/test/indeximport-issue72/index:go_default_library",
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
        "//vendor/github.com/gogo/protobuf/test/indeximport-issue72/index:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
