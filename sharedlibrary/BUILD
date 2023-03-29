package(default_visibility = ["//visibility:public"])

load("@vaticle_bazel_distribution//maven:rules.bzl", "assemble_maven", "deploy_maven")

java_library(
name = "sharedlibrary",
srcs = glob(["src/main/java/com/github/yeshamavani/*.java"]),
visibility = ["//visibility:public"],
tags = [
    "manual",
    "maven_coordinates=io.github.yeshamavani:sharedlibrary:{pom_version}"
],
)

assemble_maven(
    name = "sharedlibrary",
    developers = {
        "1" : ["name=Yesha Mavani",
                           "email=nyesha.mavani@sourcefuse.com",
                           "organization=io.github.yeshamavani",]
    },
    license = "mit",
        project_description = "MavenPublish - sharedlibrary",
        project_name = "sharedlibrary",
        project_url = "https://github.com/yeshamavani/mavenpublish",
        scm_url = "https://github.com/yeshamavani/mavenpublish.git",
        tags = ["manual"],
        target = "//sharedlibrary:sharedlibrary",
        version_file = "//central-sync:VERSION",
        workspace_refs = "//central-sync:workspace_refs.json",
)

deploy_maven(
    name = "deploy-sharedlibrary",
    release = "https://oss.sonatype.org/service/local/staging/deploy/maven2/",
    snapshot = "https://oss.sonatype.org/content/repositories/snapshots",
    tags = ["manual"],
    target = ":sharedlibrary",
)
