load("@rules_swift//swift:swift_compiler_plugin.bzl", "swift_compiler_plugin")
load("@rules_swift//swift:swift.bzl", "swift_library")

package(default_visibility = ["//visibility:public"])

swift_compiler_plugin(
    name = "ComposableArchitectureMacros",
    srcs = glob(["ComposableArchitectureMacros/*.swift"]),
    deps = [
        "@swiftpkg_swift_syntax//:Sources_SwiftCompilerPlugin",
        "@swiftpkg_swift_syntax//:Sources_SwiftSyntaxMacros",
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
        "@swiftpkg_swift_case_paths//:Sources_CasePaths",
        "@swiftpkg_combine_schedulers//:Sources_CombineSchedulers",
        "@swiftpkg_swift_concurrency_extras//:Sources_ConcurrencyExtras",
        "@swiftpkg_swift_custom_dump//:Sources_CustomDump",
        "@swiftpkg_swift_dependencies//:Sources_Dependencies",
        "@swiftpkg_swift_dependencies//:Sources_DependenciesMacros",
        "@swiftpkg_swift_identified_collections//:Sources_IdentifiedCollections",
        "@swiftpkg_swift_collections//:Sources_OrderedCollections",
        "@swiftpkg_swiftui_navigation//:Sources_SwiftUINavigationCore",
        "@swiftpkg_xctest_dynamic_overlay//:Sources_XCTestDynamicOverlay",
    ],
    plugins = [
        ":ComposableArchitectureMacros",
    ],
)