load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

package(default_visibility = ["//visibility:public"])

load("@bazel_gazelle//:def.bzl", "gazelle")

gazelle(
    name = "gazelle",
    external = "vendored",
    prefix = "github.com/tools/godep",
)

go_library(
    name = "go_default_library",
    srcs = [
        "dep.go",
        "diff.go",
        "doc.go",
        "errors.go",
        "get.go",
        "go.go",
        "godepfile.go",
        "license.go",
        "list.go",
        "main.go",
        "msg.go",
        "path.go",
        "pkg.go",
        "restore.go",
        "rewrite.go",
        "save.go",
        "update.go",
        "util.go",
        "vcs.go",
        "version.go",
    ],
    importpath = "github.com/tools/godep",
    deps = [
        "//vendor/github.com/kr/fs:go_default_library",
        "//vendor/github.com/kr/pretty:go_default_library",
        "//vendor/github.com/pmezard/go-difflib/difflib:go_default_library",
        "//vendor/golang.org/x/tools/go/vcs:go_default_library",
    ],
)

go_binary(
    name = "godep",
    embed = [":go_default_library"],
    importpath = "github.com/tools/godep",
)

go_test(
    name = "go_default_test",
    srcs = [
        "dep_test.go",
        "diff_test.go",
        "license_test.go",
        "match_test.go",
        "rewrite_test.go",
        "save_test.go",
        "update_test.go",
        "vcs_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "github.com/tools/godep",
)
