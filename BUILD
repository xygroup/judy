cc_inc_library(
name = "Judy",
hdrs = [
"src/Judy.h",
],
deps=[
":JudyImpl",
],
prefix="src",
visibility = ["//visibility:public"],
)


COPTS = [
"-std=c99",
"-W",
"-Wall",
"-Wstrict-prototypes",
"-Wmissing-prototypes",
"-DJU_64BIT",
"-m64",
"-IJudy",
"-Isrc",
"-Isrc/JudyCommon",
]

COMMON_HDRS = [
"src/JudyCommon/Judy.h",
"src/JudyCommon/JudyPrivate.h",
"src/JudyCommon/JudyPrivateBranch.h",
"src/JudyCommon/JudyPrivate1L.h",
]

cc_library(
name = "JudyImpl",
hdrs = COMMON_HDRS,
deps=[
":Judy1",
":JudyL",
":JudyHS",
":JudySL",
],
copts=COPTS + [
],
linkstatic=1,
visibility = ["//visibility:private"],
)

cc_library(
  name = "JudyMalloc",
  hdrs = COMMON_HDRS,
  srcs = [
    "src/JudyCommon/JudyMalloc.c",
  ],
  copts=COPTS + [
  ],
  linkstatic=1,
  visibility = ["//visibility:private"],
)

cc_library(
name = "Judy1",
hdrs = COMMON_HDRS + [
"src/JudyCommon/Judy1.h",
],
srcs = [
"src/JudyCommon/JudyGet.c",
"src/JudyCommon/JudyTables.c",
"src/JudyCommon/JudyIns.c",
"src/JudyCommon/JudyInsArray.c",
"src/JudyCommon/JudyDel.c",
"src/JudyCommon/JudyCascade.c",
"src/JudyCommon/JudyCount.c",
"src/JudyCommon/JudyCreateBranch.c",
"src/JudyCommon/JudyDecascade.c",
"src/JudyCommon/JudyFirst.c",
"src/JudyCommon/JudyFreeArray.c",
"src/JudyCommon/JudyInsertBranch.c",
"src/JudyCommon/JudyMallocIF.c",
"src/JudyCommon/JudyMemActive.c",
"src/JudyCommon/JudyMemUsed.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
":1next",
":1prev",
":1count",
":1inline",
],
copts = COPTS + [
"-DJUDY1",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "1next",
hdrs = COMMON_HDRS + [
"src/JudyCommon/Judy1.h",
],
srcs = [
"src/JudyCommon/JudyPrevNext.c",
"src/JudyCommon/JudyPrevNextEmpty.c",
],
copts = COPTS + [
"-DJUDY1",
"-DJUDYNEXT",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "1prev",
hdrs = COMMON_HDRS + [
"src/JudyCommon/Judy1.h",
],
srcs = [
"src/JudyCommon/JudyPrevNext.c",
"src/JudyCommon/JudyPrevNextEmpty.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDY1",
"-DJUDYPREV",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "1count",
hdrs = COMMON_HDRS + [
"src/JudyCommon/Judy1.h",
],
srcs = [
"src/JudyCommon/JudyByCount.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDY1",
"-DNOSMARTJBB",
"-DNOSMARTJBU",
"-DNOSMARTJLB",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "1inline",
hdrs = COMMON_HDRS + [
"src/JudyCommon/Judy1.h",
],
srcs = [
"src/JudyCommon/JudyGet.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDY1",
"-DJUDYGETINLINE",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "JudyHS",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyHS.h",
],
srcs = [
"src/JudyCommon/JudyHS.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDYHS",
"-DJUDYGETINLINE",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "JudyL",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyL.h",
],
srcs = [
"src/JudyCommon/JudyCascade.c",
"src/JudyCommon/JudyTables.c",
"src/JudyCommon/JudyCount.c",
"src/JudyCommon/JudyCreateBranch.c",
"src/JudyCommon/JudyDecascade.c",
"src/JudyCommon/JudyDel.c",
"src/JudyCommon/JudyFirst.c",
"src/JudyCommon/JudyFreeArray.c",
"src/JudyCommon/JudyGet.c",
"src/JudyCommon/JudyInsArray.c",
"src/JudyCommon/JudyIns.c",
"src/JudyCommon/JudyInsertBranch.c",
"src/JudyCommon/JudyMallocIF.c",
"src/JudyCommon/JudyMemActive.c",
"src/JudyCommon/JudyMemUsed.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
":Lnext",
":Lprev",
":Lcount",
":Linline",
],
copts = COPTS + [
"-DJUDYL",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "Lnext",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyL.h",
],
srcs = [
"src/JudyCommon/JudyPrevNext.c",
"src/JudyCommon/JudyPrevNextEmpty.c",
],
copts = COPTS + [
"-DJUDYL",
"-DJUDYNEXT",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "Lprev",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyL.h",
],
srcs = [
"src/JudyCommon/JudyPrevNext.c",
"src/JudyCommon/JudyPrevNextEmpty.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDYL",
"-DJUDYPREV",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "Lcount",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyL.h",
],
srcs = [
"src/JudyCommon/JudyByCount.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDYL",
"-DNOSMARTJBB",
"-DNOSMARTJBU",
"-DNOSMARTJLB",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "Linline",
hdrs = COMMON_HDRS + [
"src/JudyCommon/JudyL.h",
],
srcs = [
"src/JudyCommon/JudyGet.c",
],
linkstatic=1,
deps=[
":JudyMalloc",
],
copts = COPTS + [
"-DJUDYL",
"-DJUDYGETINLINE",
],
visibility = ["//visibility:private"],
)

cc_library(
name = "JudySL",
hdrs = COMMON_HDRS,
srcs = [
"src/JudyCommon/JudySL.c",
],
copts = COPTS + [
],
linkstatic=1,
deps=[
":JudyMalloc",
],
visibility = ["//visibility:private"],
)
