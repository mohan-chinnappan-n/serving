# Description: Example TensorFlow model export.

package(
    default_visibility = [
        "//tensorflow_serving:internal",
    ],
    features = [
        "-layering_check",
        "-parse_headers",
    ],
)

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
)

py_binary(
    name = "export_half_plus_two",
    srcs = [
        "export_half_plus_two.py",
    ],
    deps = [
        "@org_tensorflow//tensorflow:tensorflow_py",
        "@org_tensorflow//tensorflow/contrib/session_bundle:exporter",
    ],
)

# Note: re-generate these files with :export_half_plus_two whenever model
# changes.
exports_files([
    "half_plus_two/00000123/export",
    "half_plus_two/00000123/export.meta",
])
