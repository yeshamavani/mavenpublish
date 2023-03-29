workspace(name = "mavenpublish")


load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

skylib_version = "0.8.0"

http_archive(
    name = "bazel_skylib",
    sha256 = "2ef429f5d7ce7111263289644d233707dba35e39696377ebab8b0bc701f7818e",
    type = "tar.gz",
    url = "https://github.com/bazelbuild/bazel-skylib/releases/download/{}/bazel-skylib.{}.tar.gz".format(skylib_version, skylib_version),
)

load("//dependencies:google_protobuf.bzl", "google_protobuf")

google_protobuf()

load("@mavenpublish//central-sync:dependencies.bzl", "rules_jvm_external", "vaticle_bazel_distribution")

rules_jvm_external()

vaticle_bazel_distribution()
load("@vaticle_bazel_distribution//maven:deps.bzl", "maven_artifacts_with_versions")

RULES_JVM_EXTERNAL_TAG = "3.1"

RULES_JVM_EXTERNAL_SHA = "e246373de2353f3d34d35814947aa8b7d0dd1a58c2f7a6c41cfeaff3007c2d14"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")
maven_install(
    artifacts = [
        "junit:junit:4.12",
        "com.google.guava:guava:28.0-jre",
    ],
    fetch_sources = True,
    repositories = [
        "https://repo.maven.apache.org/maven2/",
        "https://mvnrepository.com/artifact",
        "https://maven-central.storage.googleapis.com",
    ],
)
