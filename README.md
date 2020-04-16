# gitlab_bazel_406_on_download_and_extract
Reproduces Bazel bug "GET returned 406 Not Acceptable" when fetching GitLab http_archive

```
# bazel sync --only=radamsa
INFO: Call stack for the definition of repository 'radamsa' which is a http_archive (rule definition at /home/pete/.cache/bazel/_bazel_pete/aa5d23528b6db1d3cf8b70d89c7b43c3/external/bazel_tools/tools/build_defs/repo/http.bzl:296:16):
 - <builtin>
 - /home/pete/wefwefwef/gitlab_bazel_406_on_download_and_extract.git/WORKSPACE:5:1
WARNING: Download from https://gitlab.com/akihe/radamsa/-/archive/v0.6/radamsa-v0.6.tar.bz2 failed: class com.google.devtools.build.lib.bazel.repository.downloader.UnrecoverableHttpException GET returned 406 Not Acceptable
ERROR: An error occurred during the fetch of repository 'radamsa':
   java.io.IOException: Error downloading [https://gitlab.com/akihe/radamsa/-/archive/v0.6/radamsa-v0.6.tar.bz2] to /home/pete/.cache/bazel/_bazel_pete/aa5d23528b6db1d3cf8b70d89c7b43c3/external/radamsa/radamsa-v0.6.tar.bz2: GET returned 406 Not Acceptable
ERROR: java.io.IOException: Error downloading [https://gitlab.com/akihe/radamsa/-/archive/v0.6/radamsa-v0.6.tar.bz2] to /home/pete/.cache/bazel/_bazel_pete/aa5d23528b6db1d3cf8b70d89c7b43c3/external/radamsa/radamsa-v0.6.tar.bz2: GET returned 406 Not Acceptable
```

```
# bazel version
Bazelisk version: development
Build label: 3.0.0
Build target: bazel-out/k8-opt/bin/src/main/java/com/google/devtools/build/lib/bazel/BazelServer_deploy.jar
Build time: Mon Apr 6 12:52:37 2020 (1586177557)
Build timestamp: 1586177557
Build timestamp as int: 1586177557
```
