load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
)
load("//pkg/version:def.bzl", "version_x_defs")

go_binary(
    name = "kubectl",
    gc_linkopts = select({
        # Mac OS X doesn't support static binaries:
        # https://developer.apple.com/library/content/qa/qa1118/_index.html
        "@io_bazel_rules_go//go/platform:darwin_amd64": [],
        "//conditions:default": [
            "-linkmode",
            "external",
            "-extldflags",
            "-static",
        ],
    }),
    importpath = "k8s.io/kubernetes/cmd/kubectl",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
    x_defs = version_x_defs(),
)

go_library(
    name = "go_default_library",
    srcs = ["kubectl.go"],
    importpath = "k8s.io/kubernetes/cmd/kubectl",
    visibility = ["//visibility:private"],
    deps = ["//vendor/k8s.io/kubernetes/cmd/kubectl/app:go_default_library"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/k8s.io/kubernetes/cmd/kubectl/app:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = [
        "//build/visible_to:cmd_kubectl_CONSUMERS",
    ],
)
