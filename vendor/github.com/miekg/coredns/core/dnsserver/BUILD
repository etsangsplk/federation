load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "address.go",
        "config.go",
        "directives.go",
        "register.go",
        "server.go",
    ],
    importpath = "github.com/miekg/coredns/core/dnsserver",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/mholt/caddy:go_default_library",
        "//vendor/github.com/mholt/caddy/caddyfile:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/metrics/vars:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/pkg/edns:go_default_library",
        "//vendor/github.com/miekg/coredns/middleware/pkg/rcode:go_default_library",
        "//vendor/github.com/miekg/coredns/request:go_default_library",
        "//vendor/github.com/miekg/dns:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["address_test.go"],
    importpath = "github.com/miekg/coredns/core/dnsserver",
    library = ":go_default_library",
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
