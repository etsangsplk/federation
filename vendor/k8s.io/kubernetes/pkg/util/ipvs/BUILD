package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "ipvs_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "ipvs_linux_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "k8s.io/kubernetes/pkg/util/ipvs",
    library = ":go_default_library",
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/docker/libnetwork/ipvs:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_library(
    name = "go_default_library",
    srcs = [
        "ipvs.go",
        "ipvs_unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "ipvs_linux.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "k8s.io/kubernetes/pkg/util/ipvs",
    deps = [
        "//vendor/k8s.io/utils/exec:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/docker/libnetwork/ipvs:go_default_library",
            "//vendor/github.com/golang/glog:go_default_library",
        ],
        "//conditions:default": [],
    }),
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
        "//vendor/k8s.io/kubernetes/pkg/util/ipvs/testing:all-srcs",
    ],
    tags = ["automanaged"],
)
