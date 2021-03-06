load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "api_service.go",
        "api_service_stub.go",
        "app.go",
        "app_add.go",
        "app_exec.go",
        "app_list.go",
        "app_rm.go",
        "app_sandbox.go",
        "app_start.go",
        "app_status.go",
        "app_stop.go",
        "attach.go",
        "cat_manifest.go",
        "config.go",
        "doc.go",
        "export.go",
        "fetch.go",
        "help.go",
        "image.go",
        "image_cat_manifest.go",
        "image_cmd_common.go",
        "image_export.go",
        "image_extract.go",
        "image_gc.go",
        "image_list.go",
        "image_render.go",
        "image_rm.go",
        "main.go",
        "metadata_service.go",
        "rkt.go",
        "stage1hash.go",
        "version.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "cli_apps.go",
            "enter.go",
            "gc.go",
            "list.go",
            "prepare.go",
            "rm.go",
            "run.go",
            "run_prepared.go",
            "status.go",
            "stop.go",
            "trust.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/coreos/rkt/rkt",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/github.com/appc/spec/aci:go_default_library",
        "//vendor/github.com/appc/spec/discovery:go_default_library",
        "//vendor/github.com/appc/spec/schema:go_default_library",
        "//vendor/github.com/appc/spec/schema/lastditch:go_default_library",
        "//vendor/github.com/appc/spec/schema/types:go_default_library",
        "//vendor/github.com/coreos/go-systemd/activation:go_default_library",
        "//vendor/github.com/coreos/rkt/api/v1alpha:go_default_library",
        "//vendor/github.com/coreos/rkt/common:go_default_library",
        "//vendor/github.com/coreos/rkt/common/apps:go_default_library",
        "//vendor/github.com/coreos/rkt/common/cgroup/v1:go_default_library",
        "//vendor/github.com/coreos/rkt/common/overlay:go_default_library",
        "//vendor/github.com/coreos/rkt/lib:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/fileutil:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/flag:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/keystore:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/label:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/lock:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/log:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/mountinfo:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/multicall:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/pod:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/set:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/tar:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/user:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/config:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/flag:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/image:go_default_library",
        "//vendor/github.com/coreos/rkt/stage0:go_default_library",
        "//vendor/github.com/coreos/rkt/store/imagestore:go_default_library",
        "//vendor/github.com/coreos/rkt/store/treestore:go_default_library",
        "//vendor/github.com/coreos/rkt/version:go_default_library",
        "//vendor/github.com/dustin/go-humanize:go_default_library",
        "//vendor/github.com/gorilla/mux:go_default_library",
        "//vendor/github.com/hashicorp/errwrap:go_default_library",
        "//vendor/github.com/hashicorp/golang-lru:go_default_library",
        "//vendor/github.com/spf13/cobra:go_default_library",
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/containernetworking/cni/pkg/types:go_default_library",
            "//vendor/github.com/coreos/rkt/networking/netinfo:go_default_library",
            "//vendor/github.com/coreos/rkt/rkt/pubkey:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_binary(
    name = "rkt",
    importpath = "github.com/coreos/rkt/rkt",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "api_service_test.go",
        "cli_apps_test.go",
        "fetch_test.go",
        "metadata_service_test.go",
        "rkt_test.go",
    ],
    importpath = "github.com/coreos/rkt/rkt",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/appc/spec/schema:go_default_library",
        "//vendor/github.com/appc/spec/schema/types:go_default_library",
        "//vendor/github.com/coreos/rkt/api/v1alpha:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/aci:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/aci/acitest:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/distribution:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/keystore:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/keystore/keystoretest:go_default_library",
        "//vendor/github.com/coreos/rkt/pkg/log:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/config:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/flag:go_default_library",
        "//vendor/github.com/coreos/rkt/rkt/image:go_default_library",
        "//vendor/github.com/coreos/rkt/store/imagestore:go_default_library",
        "//vendor/github.com/spf13/pflag:go_default_library",
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
        "//vendor/github.com/coreos/rkt/rkt/config:all-srcs",
        "//vendor/github.com/coreos/rkt/rkt/flag:all-srcs",
        "//vendor/github.com/coreos/rkt/rkt/image:all-srcs",
        "//vendor/github.com/coreos/rkt/rkt/pubkey:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
