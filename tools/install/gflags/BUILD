# -*- python -*-

load(
    "@drake//tools:install.bzl",
    "cmake_config",
    "install",
    "install_cmake_config",
)
load("//tools:lint.bzl", "add_lint_tests")

package(default_visibility = ["//visibility:public"])

cmake_config(
    cps_file_name = "gflags.cps",
    package = "gflags",
)

install_cmake_config(package = "gflags")  # Creates rule :install_cmake_config.

install(
    name = "install",
    targets = ["@com_github_gflags_gflags//:gflags"],
    hdr_dest = "include",
    hdr_strip_prefix = ["include"],
    guess_hdrs = "PACKAGE",
    guess_hdrs_exclude = [
        "config.h",
        "src/mutex.h",
        "src/util.h",
    ],
    docs = ["@com_github_gflags_gflags//:COPYING.txt"],
    doc_dest = "share/doc/gflags",
    allowed_externals = ["@com_github_gflags_gflags//:gflags"],
    visibility = ["//:__pkg__"],
    deps = [":install_cmake_config"],
)

add_lint_tests()
