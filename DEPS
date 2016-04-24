vars = {
  "root_dir": "src",
  "googlecode_url": "http://%s.googlecode.com/svn",

  "skia_revision": "15018",
}

deps = {
  "src/third_party/skia/":
      (Var("googlecode_url") % "skia") + "/trunk_no_commit@" + Var("skia_revision"),

  "src/tools/gyp":
      (Var("googlecode_url") % "gyp") + "/trunk_no_commit@" + Var("skia_revision"),

  "src/tools/":
      File((Var("googlecode_url") % "skia") + "/trunk_no_commit/tools/find_mac_sdk.py@" +
          Var("skia_revision")),
}

hooks = [
  {
    # A change to a .gyp, .gypi or to GYP itself should run the generator.
    "name": "gyp",
    "pattern": ".",
    "action": ["python", "src/build/gyp_using_skia"]
  }
]
