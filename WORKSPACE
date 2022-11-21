container_pull(
  name="redmine",
  registry="index.docker.io",
  repository="redmine",
  digest="sha256:aac20cf437cb32b160a853b0abe3fb82b0ec91052ebe51eabc9a3474a34e5cc9",
  tag="5.0.1"
)


workspace(name = "angular_bazel_example")

go_repository(
    name = "com_github_bitly_go-nsq",
    importpath = "github.com/bitly/go-nsq",
    tag = "v1.0.5"
)

go_repository(
   name = "com_github_google_uuid",
   importpath = "github.com/google/uuid",
   commit = "dec09d789f3dba190787f8b4454c7d3c936fed9e"
)

go_repository(
    name = "com_gopkgin_mgo_v2",
    importpath = "gopkg.in/mgo.v2",
    tag = "v2"
)

git_repository(
    name = "build_bazel_rules_nodejs",
    remote = "https://github.com/bazelbuild/rules_nodejs.git",
    tag = "0.3.1",
)

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories")
node_repositories(package_json = ["//:package.json"])

git_repository(
    name = "build_bazel_rules_typescript",
    remote = "https://github.com/bazelbuild/rules_typescript.git",
    tag = "0.6.1",
)

load("@build_bazel_rules_typescript//:defs.bzl", "ts_repositories")

ts_repositories()

http_archive(
    name="distroless",
    sha256="f7a6ecfb8174a1dd4713ea3b21621072996ada7e8f1a69e6ae7581be137c6dd6",
    strip_prefix="distroless-446923c3756ceeaa75888f52fcbdd48bb314fbf8",
    urls=["https://github.com/GoogleContainerTools/distroless/archive/446923c3756ceeaa75888f52fcbdd48bb314fbf8.tar.gz"]
)

http_archive(
  name = "bazel_toolchains",
    sha256 = "4b1468b254a572dbe134cc1fd7c6eab1618a72acd339749ea343bd8f55c3b7eb",
    strip_prefix = "bazel-toolchains-d665ccfa3e9c90fa789671bf4ef5f7c19c5715c4",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-toolchains/archive/d665ccfa3e9c90fa789671bf4ef5f7c19c5715c4.tar.gz",
        "https://github.com/bazelbuild/bazel-toolchains/archive/d665ccfa3e9c90fa789671bf4ef5f7c19c5715c4.tar.gz",
    ],
)

http_archive(
    name = "rules_nodejs",
    sha256 = "5aef09ed3279aa01d5c928e3beb248f9ad32dde6aafe6373a8c994c3ce643064",
    urls = [
      "https://github.com/bazelbuild/rules_nodejs/releases/download/5.5.3/rules_nodejs-core-5.5.3.tar.gz"
    ],
)

local_repository(
    name = "angular",
    path = "node_modules/@angular/bazel",
)

local_repository(
    name = "rxjs",
    path = "node_modules/rxjs/src",
)

git_repository(
    name = "io_bazel_rules_sass",
    remote = "https://github.com/bazelbuild/rules_sass.git",
    tag = "0.0.3",
)

load("@io_bazel_rules_sass//sass:sass.bzl", "sass_repositories")

sass_repositories()

git_repository(
    name = "com_github_bazelbuild_buildtools",
    remote = "https://github.com/bazelbuild/buildtools.git",
    # Note, this commit matches the version of buildifier in angular/ngcontainer
    commit = "b3b620e8bcff18ed3378cd3f35ebeb7016d71f71",
)

http_archive(
    name = "io_bazel_rules_go",
    url = "https://github.com/bazelbuild/rules_go/releases/download/0.7.1/rules_go-0.7.1.tar.gz",
    sha256 = "341d5eacef704415386974bc82a1783a8b7ffbff2ab6ba02375e1ca20d9b031c",
)

http_archive(
    name = "bazel_skylib",
    sha256 = "b5f6abe419da897b7901f90cbab08af958b97a8f3575b0d3dd062ac7ce78541f",
    strip_prefix = "bazel-skylib-0.5.0",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/archive/0.5.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/archive/0.5.0.tar.gz",
    ],
)

http_archive(
    name="distroless",
    sha256="f7a6ecfb8174a1dd4713ea3b21621072996ada7e8f1a69e6ae7581be137c6dd6",
    strip_prefix="distroless-446923c3756ceeaa75888f52fcbdd48bb314fbf8",
    urls=["https://github.com/GoogleContainerTools/distroless/archive/446923c3756ceeaa75888f52fcbdd48bb314fbf8.tar.gz"]
)

load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")
maybe(
  http_archive,
  name = "io_bazel_rules_go",
  sha256 = "2b1641428dff9018f9e85c0384f03ec6c10660d935b750e3fa1492a281a53b0f",
  url = "https://github.com/bazelbuild/rules_go/releases/download/v0.29.0/rules_go-v0.29.0.zip",
)
maybe(
    http_archive,
    name = "bazel_gazelle",
    sha256 = "de69a09dc70417580aabf20a28619bb3ef60d038470c7cf8442fafcf627c21cb",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
    ],
)
maybe(
    go_repository,
    name = "com_github_pkg_errors",
    commit = "816c9085562cd7ee03e7f8188a1cfd942858cded",
    importpath = "github.com/pkg/errors",
)

load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains")

go_rules_dependencies()

go_register_toolchains()

container_pull(
    name = "py3_image_base",
    digest = "sha256:d5a717649fd93ea5b9c430d7f84e4c37ba219eb53bd73ed1d4a5a98e9edd84a7",
    registry = "gcr.io",
    repository = "distroless/python3-debian10",
    tag = "latest",
)

http_file(
    name="distroless",
    sha256="f7a6ecfb8174a1dd4713ea3b21621072996ada7e8f1a69e6ae7581be137c6dd6",
    strip_prefix="distroless-446923c3756ceeaa75888f52fcbdd48bb314fbf8",
    urls=["https://github.com/GoogleContainerTools/distroless/archive/446923c3756ceeaa75888f52fcbdd48bb314fbf8.tar.gz"]
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")

http_archive(
    name = "GBDeviceInfo",
    url = "https://github.com/lmirosevic/GBDeviceInfo/archive/6.3.0.tar.gz",
    sha256 = "d7666275dff039407ea467c3083b83e24934101777c8b55b6b1b3b7e9a9e220b",
    strip_prefix = "GBDeviceInfo-6.3.0/GBDeviceInfo"
)

http_archive(
    name = "com_github_nelhage_rules_boost",
    url = "https://github.com/nelhage/rules_boost/archive/135d46b4c9423ee7d494c78a21ff621bc73c12f3.tar.gz",
    sha256 = "3651f5dda0f7296e4cecafacc7f9d1f274be0fd64e30bebd74e28ffba28fe77f",
    strip_prefix = "rules_boost-135d46b4c9423ee7d494c78a21ff621bc73c12f3",
)
load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")
boost_deps()

http_archive(
    name = "GBDeviceInfo-zip",
    url = "https://github.com/lmirosevic/GBDeviceInfo/archive/6.3.0.zip",
    sha256 = "4ef4320c4880fd64cfb7f42132f4b02fa626bccf1ba3e1a71dfbfcb50735f141",
    strip_prefix = "GBDeviceInfo-6.3.0/GBDeviceInfo"
)

http_archive(
    name = "com_github_nelhage_rules_boost-zip",
    url = "https://github.com/nelhage/rules_boost/archive/135d46b4c9423ee7d494c78a21ff621bc73c12f3.zip",
    sha256 = "de8aac034cabe4a9ba5f7a33b9523862bf76c245a6c554c0e737f591bb7c7aeb",
    strip_prefix = "rules_boost-135d46b4c9423ee7d494c78a21ff621bc73c12f3",
)

maybe(
  http_archive,
  name = "io_bazel_rules_go",
  sha256 = "2b1641428dff9018f9e85c0384f03ec6c10660d935b750e3fa1492a281a53b0f",
  url = "https://github.com/bazelbuild/rules_go/releases/download/v0.29.0/rules_go-v0.29.0.zip",
)

    # Eigen already had a good BUILD file from Tensorflow.
# http_archive(
#     name = "rules_foreign_cc",
#     url = "https://github.com/bazelbuild/rules_foreign_cc/archive/dfccdce2c9d1063c59ddd331b94eb7cb528a96ee.tar.gz",
#     sha256 = "5469ef8b4e2c475de443c13290cf91ba7d1255899442b1e42fcb7fcdee8ceed8",
#     strip_prefix = "rules_foreign_cc-dfccdce2c9d1063c59ddd331b94eb7cb528a96ee",
# )
# load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")
# rules_foreign_cc_dependencies()
# # Usage is a little weird, and depends
# FOREIGN_CC_EXPOSE_ALL_FILES = """filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:public"])"""


########################################
# C++ & Cross-Platform Libraries

# Boost.
# Famous C++ library that gives rise to many new additions in the C++ standard library.
# See https://github.com/nelhage/rules_boost, recommended from https://docs.bazel.build/versions/master/rules.html
http_archive(
    name = "com_github_nelhage_rules_boost",
    url = "https://github.com/nelhage/rules_boost/archive/98495a618246683c9058dd87c2c78a2c06087999.tar.gz",
    sha256 = "f92cb7ed66a5b24f97a7fc3917407f808c70d2689273bdd68f93d70a379d22d3",
    strip_prefix = "rules_boost-98495a618246683c9058dd87c2c78a2c06087999",
)
load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")
boost_deps() # Also pulls in a bunch of boost depenencies if you don't have them already. See https://github.com/nelhage/rules_boost/blob/master/boost/boost.bzl

# Copyright 2017 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
"""Rules for load all dependencies of rules_docker."""

load(
    "@bazel_tools//tools/build_defs/repo:http.bzl",
    "http_archive",
    "http_file",
)
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")
load(
    "@io_bazel_rules_docker//toolchains/docker:toolchain.bzl",
    _docker_toolchain_configure = "toolchain_configure",
)

# The release of the github.com/google/containerregistry to consume.
CONTAINERREGISTRY_RELEASE = "v0.0.35"

_local_tool_build_template = """
sh_binary(
    name = "{name}",
    srcs = ["bin/{name}"],
    visibility = ["//visibility:public"],
)
"""

def _local_tool(repository_ctx):
    rctx = repository_ctx
    realpath = rctx.which(rctx.name)
    rctx.symlink(realpath, "bin/%s" % rctx.name)
    rctx.file(
        "WORKSPACE",
        'workspace(name = "{}")\n'.format(rctx.name),
    )
    rctx.file(
        "BUILD",
        _local_tool_build_template.format(name = rctx.name),
    )

local_tool = repository_rule(
    local = True,
    implementation = _local_tool,
)

def repositories():
    """Download dependencies of container rules."""
    excludes = native.existing_rules().keys()

    # TODO(ngiraldo): Remove after 1cf75b9dab3e0bb2ffa3014d6e657aa486b1c7bf is in a Bazel release
    # https://github.com/bazelbuild/bazel/commit/1cf75b9dab3e0bb2ffa3014d6e657aa486b1c7bf
    if "bazel_source" not in excludes:
        http_archive(
            name = "bazel_source",
            sha256 = "3f5441ab5bf403bc44e31bf018ed994d02a1bd2dbf350eface5bf343bc7dff4c",
            strip_prefix = "bazel-1cf75b9dab3e0bb2ffa3014d6e657aa486b1c7bf",
            urls = [("https://github.com/bazelbuild/bazel/archive/1cf75b9dab3e0bb2ffa3014d6e657aa486b1c7bf.tar.gz")],
        )

    if "puller" not in excludes:
        http_file(
            name = "puller",
            executable = True,
            sha256 = "480baba71500f837672093799de9c5492990a04d327a0b9bb3e1f75eecbbdfde",
            urls = [("https://storage.googleapis.com/containerregistry-releases/" +
                     CONTAINERREGISTRY_RELEASE + "/puller.par")],
        )

    if "importer" not in excludes:
        http_file(
            name = "importer",
            executable = True,
            sha256 = "dad924671e4fee84b7ddfb1cd06b988d7f4e18836b81f0c6ae8e144ae046a18f",
            urls = [("https://storage.googleapis.com/containerregistry-releases/" +
                     CONTAINERREGISTRY_RELEASE + "/importer.par")],
        )

    if "containerregistry" not in excludes:
        http_archive(
            name = "containerregistry",
            sha256 = "98a7d40b7b45dc76f031c9e17728dddb963f8ec28a1ee4d18693e57155d198f8",
            strip_prefix = "containerregistry-" + CONTAINERREGISTRY_RELEASE[1:],
            urls = [("https://github.com/google/containerregistry/archive/" +
                     CONTAINERREGISTRY_RELEASE + ".tar.gz")],
        )

    # TODO(mattmoor): Remove all of this (copied from google/containerregistry)
    # once transitive workspace instantiation lands.

    if "httplib2" not in excludes:
        # TODO(mattmoor): Is there a clean way to override?
        http_archive(
            name = "httplib2",
            build_file_content = """
py_library(
   name = "httplib2",
   srcs = glob(["**/*.py"]),
   data = ["cacerts.txt"],
   visibility = ["//visibility:public"]
)""",
            sha256 = "d9f568c183d1230f271e9c60bd99f3f2b67637c3478c9068fea29f7cca3d911f",
            strip_prefix = "httplib2-0.11.3/python2/httplib2/",
            type = "tar.gz",
            urls = ["https://codeload.github.com/httplib2/httplib2/tar.gz/v0.11.3"],
        )

    # Used by oauth2client
    if "six" not in excludes:
        # TODO(mattmoor): Is there a clean way to override?
        http_archive(
            name = "six",
            build_file_content = """
# Rename six.py to __init__.py
genrule(
    name = "rename",
    srcs = ["six.py"],
    outs = ["__init__.py"],
    cmd = "cat $< >$@",
)
py_library(
   name = "six",
   srcs = [":__init__.py"],
   visibility = ["//visibility:public"],
)""",
            sha256 = "e24052411fc4fbd1f672635537c3fc2330d9481b18c0317695b46259512c91d5",
            strip_prefix = "six-1.9.0/",
            type = "tar.gz",
            urls = ["https://pypi.python.org/packages/source/s/six/six-1.9.0.tar.gz"],
        )

    # Used for authentication in containerregistry
    if "oauth2client" not in excludes:
        # TODO(mattmoor): Is there a clean way to override?
        http_archive(
            name = "oauth2client",
            build_file_content = """
py_library(
   name = "oauth2client",
   srcs = glob(["**/*.py"]),
   visibility = ["//visibility:public"],
   deps = [
     "@httplib2//:httplib2",
     "@six//:six",
   ]
)""",
            sha256 = "7230f52f7f1d4566a3f9c3aeb5ffe2ed80302843ce5605853bee1f08098ede46",
            strip_prefix = "oauth2client-4.0.0/oauth2client/",
            type = "tar.gz",
            urls = ["https://codeload.github.com/google/oauth2client/tar.gz/v4.0.0"],
        )

    # Used for parallel execution in containerregistry
    if "concurrent" not in excludes:
        # TODO(mattmoor): Is there a clean way to override?
        http_archive(
            name = "concurrent",
            build_file_content = """
py_library(
   name = "concurrent",
   srcs = glob(["**/*.py"]),
   visibility = ["//visibility:public"]
)""",
            sha256 = "a7086ddf3c36203da7816f7e903ce43d042831f41a9705bc6b4206c574fcb765",
            strip_prefix = "pythonfutures-3.0.5/concurrent/",
            type = "tar.gz",
            urls = ["https://codeload.github.com/agronholm/pythonfutures/tar.gz/3.0.5"],
        )

    # For packaging python tools.
    if "subpar" not in excludes:
        http_archive(
            name = "subpar",
            sha256 = "7ab6ab37ede82255e00c0456846a1428b20e8813f77d83bcf54ddd59ba34377a",
            # Commit from 2019-03-07.
            strip_prefix = "subpar-0356bef3fbbabec5f0e196ecfacdeb6db62d48c0",
            urls = ["https://github.com/google/subpar/archive/0356bef3fbbabec5f0e196ecfacdeb6db62d48c0.tar.gz"],
        )

    if "structure_test_linux" not in excludes:
        http_file(
            name = "structure_test_linux",
            executable = True,
            sha256 = "cfdfedd77c04becff0ea16a4b8ebc3b57bf404c56e5408b30d4fbb35853db67c",
            urls = ["https://storage.googleapis.com/container-structure-test/v1.8.0/container-structure-test-linux-amd64"],
        )

    if "structure_test_darwin" not in excludes:
        http_file(
            name = "structure_test_darwin",
            executable = True,
            sha256 = "14e94f75112a8e1b08a2d10f2467d27db0b94232a276ddd1e1512593a7b7cf5a",
            urls = ["https://storage.googleapis.com/container-structure-test/v1.8.0/container-structure-test-darwin-amd64"],
        )

    # For bzl_library.
    if "bazel_skylib" not in excludes:
        http_archive(
            name = "bazel_skylib",
            sha256 = "eb5c57e4c12e68c0c20bc774bfbc60a568e800d025557bc4ea022c6479acc867",
            strip_prefix = "bazel-skylib-0.6.0",
            urls = ["https://github.com/bazelbuild/bazel-skylib/archive/0.6.0.tar.gz"],
        )

    maybe(
        http_archive,
        name = "io_bazel_stardoc",
        sha256 = "c9794dcc8026a30ff67cf7cf91ebe245ca294b20b071845d12c192afe243ad72",
        urls = [
            "https://mirror.bazel.build/github.com/bazelbuild/stardoc/releases/download/0.5.0/stardoc-0.5.0.tar.gz",
            "https://github.com/bazelbuild/stardoc/releases/download/0.5.0/stardoc-0.5.0.tar.gz",
        ],
    )

    if "gzip" not in excludes:
        local_tool(
            name = "gzip",
        )

    native.register_toolchains(
        # Register the default docker toolchain that expects the 'docker'
        # executable to be in the PATH
        "@io_bazel_rules_docker//toolchains/docker:default_linux_toolchain",
        "@io_bazel_rules_docker//toolchains/docker:default_windows_toolchain",
        "@io_bazel_rules_docker//toolchains/docker:default_osx_toolchain",
    )

    if "docker_config" not in excludes:
        # Automatically configure the docker toolchain rule to use the default
        # docker binary from the system path
        _docker_toolchain_configure(name = "docker_config")

container_pull(
    name="hasura",
    registry="index.docker.io",
    repository="hasura/graphql-engine",
    # v1.0.0-alpha31.cli-migrations 11/28
    digest="sha256:a4e8d8c444ca04fe706649e82263c9f4c2a4229bc30d2a64561b5e1d20cc8548",
    tag="v1.0.0-alpha31.cli-migrations"
)
