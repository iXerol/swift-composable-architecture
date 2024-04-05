load("@rules_swift//swift:swift_compiler_plugin.bzl", "swift_compiler_plugin")
load("@rules_swift//swift:swift.bzl", "swift_library")

package(default_visibility = ["//visibility:public"])

swift_compiler_plugin(
    name = "ComposableArchitectureMacros",
    srcs = glob(["ComposableArchitectureMacros/*.swift"]),
    deps = [
        "@swiftpkg_swift_syntax//:SwiftCompilerPlugin",
        "@swiftpkg_swift_syntax//:SwiftSyntaxMacros",
    ],
)

swift_library(
    name = "ComposableArchitecture",
    module_name = "ComposableArchitecture",
    srcs = glob([
        "ComposableArchitecture/**/*.swift",
    ],exclude = [
        "ComposableArchitecture/Documentation.docc/**/*.swift"
    ]),
    deps = [
        "@swiftpkg_swift_case_paths//:CasePaths",
        "@swiftpkg_combine_schedulers//:CombineSchedulers",
        "@swiftpkg_swift_concurrency_extras//:ConcurrencyExtras",
        "@swiftpkg_swift_custom_dump//:CustomDump",
        "@swiftpkg_swift_dependencies//:Dependencies",
        "@swiftpkg_swift_dependencies//:DependenciesMacros",
        "@swiftpkg_swift_identified_collections//:IdentifiedCollections",
        "@swiftpkg_swift_collections//:OrderedCollections",
        "@swiftpkg_swiftui_navigation//:SwiftUINavigationCore",
        "@swiftpkg_xctest_dynamic_overlay//:XCTestDynamicOverlay",
    ],
    plugins = [
        ":ComposableArchitectureMacros",
    ],
)