
load("@bis//:refresh_compile_commands.bzl", "refresh_compile_commands")
load("@bis//:refresh_launch_json.bzl", "refresh_launch_json")
refresh_compile_commands(
  name = "refresh_compile_commands",
  targets = [
    "//Examples/SpeechRecognition/SpeechRecognition:SpeechRecognition_app"
  ],
  optionals = "--compilation_mode=dbg --cpu=ios_x86_64 --features=oso_prefix_is_pwd --profile .bis/bis_bazel_profile",
  tags = ["manual"],
)

refresh_launch_json(
  name = "refresh_launch_json",
  target = "//Examples/SpeechRecognition/SpeechRecognition:SpeechRecognition_app",
  tags = ["manual"],
  testonly = True,
)

