load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "blobstore.go",
        "read.go",
    ],
    importpath = "google.golang.org/appengine/blobstore",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/appengine:go_default_library",
        "//vendor/google.golang.org/appengine/datastore:go_default_library",
        "//vendor/google.golang.org/appengine/internal:go_default_library",
        "//vendor/google.golang.org/appengine/internal/base:go_default_library",
        "//vendor/google.golang.org/appengine/internal/blobstore:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["blobstore_test.go"],
    importpath = "google.golang.org/appengine/blobstore",
    library = ":go_default_library",
    deps = [
        "//vendor/google.golang.org/appengine:go_default_library",
        "//vendor/google.golang.org/appengine/internal/aetesting:go_default_library",
        "//vendor/google.golang.org/appengine/internal/blobstore:go_default_library",
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
