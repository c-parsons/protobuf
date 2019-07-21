workspace(name = "com_google_protobuf")

local_repository(
    name = "com_google_protobuf_examples",
    path = "examples",
)

local_repository(
    name = "submodule_gmock",
    path = "third_party/googletest",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("//:protobuf_deps.bzl", "protobuf_deps")

# Load common dependencies.
protobuf_deps()

http_archive(
    name = "six",
    build_file = "@//:third_party/six.BUILD",
    sha256 = "d16a0141ec1a18405cd4ce8b4613101da75da0e9a7aec5bdd4fa804d0e0eba73",
    urls = ["https://pypi.python.org/packages/source/s/six/six-1.12.0.tar.gz"],
)

bind(
    name = "python_headers",
    actual = "//util/python:python_headers",
)

bind(
    name = "gtest",
    actual = "@submodule_gmock//:gtest",
)

bind(
    name = "gtest_main",
    actual = "@submodule_gmock//:gtest_main",
)

maven_jar(
    name = "guava_maven",
    artifact = "com.google.guava:guava:18.0",
)

bind(
    name = "guava",
    actual = "@guava_maven//jar",
)

maven_jar(
    name = "gson_maven",
    artifact = "com.google.code.gson:gson:2.7",
)

bind(
    name = "gson",
    actual = "@gson_maven//jar",
)

maven_jar(
    name = "error_prone_annotations_maven",
    artifact = "com.google.errorprone:error_prone_annotations:2.3.2",
)

bind(
    name = "error_prone_annotations",
    actual = "@error_prone_annotations_maven//jar",
)
