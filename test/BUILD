
subinclude("//build_defs:cmake")

cmake_configure_file(
  name = "test",
  src = "config.h.in",
  out = "config.h",
  variables =
  {
    "enabledVar": "",
    "enabledTabedVar": "",
    "enabledSpacedVar":"",
    "enabledStringVar":"",
    "enabledTabedStringVar":"",
    "enabled01":"",
    "enabledTabed01":"",
    "AtVarEnabled":"true",
    "DollarVarEnabled":"true",
    "CacheVarEnabled":"true"
  }
)

genrule(
  name = "testOut",
  cmd = "",
  deps = [":test"]
)