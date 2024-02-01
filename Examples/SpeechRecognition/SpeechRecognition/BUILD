load("@rules_swift//swift:swift.bzl","swift_library")
load("@rules_apple//apple:ios.bzl","ios_application")
load("@rules_apple//apple:versioning.bzl","apple_bundle_version")
load(
    "@rules_xcodeproj//xcodeproj:defs.bzl",
    "top_level_target",
    "xcodeproj",
)
package(default_visibility = [":__pkg__"])

swift_library(
    name = "SpeechRecognition",
	module_name = "SpeechRecognition",
    srcs = glob([
        "**/*.swift",
    ]),
    deps = [
		"//Sources:ComposableArchitecture",
    ],
	plugins = [
		"//Sources:ComposableArchitectureMacros",
	],
)

apple_bundle_version(
    name = "version",
    build_version = "1.0.0",
    short_version_string = "1.0",
)

ios_application(
    name = "SpeechRecognition_app",
    bundle_id = "co.pointfree.SpeechRecognition",
    families = [
        "iphone",
        "ipad",
    ],
    infoplists = [
		"Info.plist",
	],
	version = ":version",
	resources = glob([
		"Resources/**"
	]),
    minimum_os_version = "17.0",
    deps = [
        ":SpeechRecognition",
    ],
    visibility = ["//visibility:public"],
)

xcodeproj(
    name = "xcodeproj",
    project_name = "SpeechRecognition_app",
    tags = ["manual"],
    top_level_targets = [
        top_level_target("//Examples/SpeechRecognition/SpeechRecognition:SpeechRecognition_app", target_environments = ["simulator"]),
    ],
    build_mode = "bazel",
)
