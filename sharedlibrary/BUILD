package(default_visibility = ["//visibility:public"])

load("@vaticle_bazel_distribution//maven:rules.bzl", "assemble_maven", "deploy_maven","java_library")

java_library(
name = "sharedlibrary",
srcs = glob(["src/main/java/com/github/yeshamavani/*.java"]),
visibility = ["//visibility:public"],
)

assemble_maven(
    name = "assemble-maven",
    developers = {
    "1": [
    "name:Yesha Mavani",
    "email:yesha.mavani@sourcefuse.com",
    "organization:com.github.yeshamavani"
    ]
    },
     license = "mit",
     project_description = "A trial monorepo for publish",
     project_name = "maven publish main project by yesha",
     project_url = "https://github.com/yeshamavani/mavenpublish",
     scm_url = "https://github.com/yeshamavani/mavenpublish.git",
    )

deploy_maven(
    name = "deploy-maven",
    release = "https://oss.sonatype.org/service/local/staging/deploy/maven2/",
    snapshot = "https://oss.sonatype.org/content/repositories/snapshots",
    tags = ["manual"],
    target = ":assemble-maven",
)