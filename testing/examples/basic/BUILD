load("@io_bazel_rules_docker//container:container.bzl", "container_image")
load("@io_bazel_rules_docker//contrib:test.bzl", "container_test")

container_image(
    name = "basic_alpine",
    base = "@alpine_linux_amd64//image",
    cmd = ["Hello World!"],
    entrypoint = ["echo"],
)

# Tests

container_test(
    name = "basic_alpine_bazel_test",
    configs = ["//basic/test_configs:basic_alpine.yaml"],
    image = ":basic_alpine",
)

container_test(
    name = "basic_alpine_dockerfile_test",
    configs = ["//basic/test_configs:basic_alpine.yaml"],
    driver = "tar",
    image = "@basic_alpine_dockerfile//image:dockerfile_image",
)
