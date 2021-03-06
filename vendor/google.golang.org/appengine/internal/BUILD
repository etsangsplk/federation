load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "api.go",
        "api_common.go",
        "app_id.go",
        "identity.go",
        "identity_vm.go",
        "internal.go",
        "main_vm.go",
        "metadata.go",
        "net.go",
        "transaction.go",
    ],
    importpath = "google.golang.org/appengine/internal",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/appengine/internal/base:go_default_library",
        "//vendor/google.golang.org/appengine/internal/datastore:go_default_library",
        "//vendor/google.golang.org/appengine/internal/log:go_default_library",
        "//vendor/google.golang.org/appengine/internal/remote_api:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "api_test.go",
        "app_id_test.go",
        "internal_vm_test.go",
        "net_test.go",
    ],
    importpath = "google.golang.org/appengine/internal",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/appengine/internal/base:go_default_library",
        "//vendor/google.golang.org/appengine/internal/remote_api:go_default_library",
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
        "//vendor/google.golang.org/appengine/internal/aetesting:all-srcs",
        "//vendor/google.golang.org/appengine/internal/app_identity:all-srcs",
        "//vendor/google.golang.org/appengine/internal/base:all-srcs",
        "//vendor/google.golang.org/appengine/internal/blobstore:all-srcs",
        "//vendor/google.golang.org/appengine/internal/capability:all-srcs",
        "//vendor/google.golang.org/appengine/internal/channel:all-srcs",
        "//vendor/google.golang.org/appengine/internal/datastore:all-srcs",
        "//vendor/google.golang.org/appengine/internal/image:all-srcs",
        "//vendor/google.golang.org/appengine/internal/log:all-srcs",
        "//vendor/google.golang.org/appengine/internal/mail:all-srcs",
        "//vendor/google.golang.org/appengine/internal/memcache:all-srcs",
        "//vendor/google.golang.org/appengine/internal/modules:all-srcs",
        "//vendor/google.golang.org/appengine/internal/remote_api:all-srcs",
        "//vendor/google.golang.org/appengine/internal/search:all-srcs",
        "//vendor/google.golang.org/appengine/internal/socket:all-srcs",
        "//vendor/google.golang.org/appengine/internal/system:all-srcs",
        "//vendor/google.golang.org/appengine/internal/taskqueue:all-srcs",
        "//vendor/google.golang.org/appengine/internal/urlfetch:all-srcs",
        "//vendor/google.golang.org/appengine/internal/user:all-srcs",
        "//vendor/google.golang.org/appengine/internal/xmpp:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
