licenses(["notice"])

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "extensions",
    srcs = ["extensions.cc"],
    hdrs = ["extensions.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "//cc/google/fhir/status",
        "//proto/stu3:annotations_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "extensions_test",
    srcs = ["extensions_test.cc"],
    data = ["//testdata/stu3:extensions"],
    deps = [
        ":extensions",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:extensions_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "util",
    srcs = ["util.cc"],
    hdrs = ["util.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "//cc/google/fhir/status",
        "//cc/google/fhir/status:statusor",
        "//cc/google/fhir/systems",
        "//proto/stu3:annotations_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "util_test",
    srcs = ["util_test.cc"],
    deps = [
        ":util",
        "//cc/google/fhir/systems",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:codes_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:metadatatypes_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_absl//absl/time",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "resource_validation",
    srcs = ["resource_validation.cc"],
    hdrs = ["resource_validation.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "//cc/google/fhir/status",
        "//cc/google/fhir/status:statusor",
        "//proto/stu3:annotations_cc_proto",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "resource_validation_test",
    srcs = ["resource_validation_test.cc"],
    deps = [
        ":resource_validation",
        "//proto/stu3:resources_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_library(
    name = "proto_util",
    srcs = ["proto_util.cc"],
    hdrs = ["proto_util.h"],
    strip_include_prefix = "//cc/",
    deps = [
        "//cc/google/fhir/status",
        "//cc/google/fhir/status:statusor",
        "@com_google_absl//absl/strings",
        "@com_google_protobuf//:protobuf",
        "@com_googlesource_code_re2//:re2",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "proto_util_test",
    srcs = ["proto_util_test.cc"],
    deps = [
        ":proto_util",
        "//cc/google/fhir/testutil:proto_matchers",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_library(
    name = "test_helper",
    testonly = 1,
    hdrs = ["test_helper.h"],
    strip_include_prefix = "//cc/",
    deps = [
        ":resource_validation",
        "//cc/google/fhir/status",
        "@com_google_absl//absl/strings",
        "@com_google_googletest//:gtest",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_library(
    name = "bundle_to_versioned_resources_converter",
    srcs = ["bundle_to_versioned_resources_converter.cc"],
    hdrs = ["bundle_to_versioned_resources_converter.h"],
    strip_include_prefix = "//cc/",
    deps = [
        ":proto_util",
        ":util",
        "//cc/google/fhir/status",
        "//cc/google/fhir/status:statusor",
        "//proto/stu3:datatypes_cc_proto",
        "//proto/stu3:resources_cc_proto",
        "//proto/stu3:version_config_cc_proto",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/time",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

cc_test(
    name = "bundle_to_versioned_resources_converter_test",
    srcs = ["bundle_to_versioned_resources_converter_test.cc"],
    data = ["//proto/stu3:version_config.textproto"],
    deps = [
        ":bundle_to_versioned_resources_converter",
        "//cc/google/fhir/testutil:proto_matchers",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)
