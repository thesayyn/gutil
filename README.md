# Gutil

This repository contains general-purpose utility functions that are currently
missing in (the open-source versions of) GoogleTest, Abseil, and Protocol
Buffers (e.g. proto matching, proto ordering, status matchers, test artifact
writers, etc).

This repository is meant to eventually go away, when better alternatives are
available directly in the mentioned libraries.

This is not an officially supported Google product.

## Cutting a Release

The version of releases follows the year, month, date, and patch format.

1.  Create a new branch with the name `release-yyyymmdd`.
2.  In the branch, the version in the
    [MODULE.bazel](https://github.com/google/gutil/blob/main/MODULE.bazel#L19)
    must be updated to match `yyyymmdd.p`, where p is the patch number
    (initially 0).
    *   Note that this branch should not be deleted to keep an archive of all
        releases and it makes it easier to add patches for a release.
3.  Create a new release on Github with the tag being in the form `yyyymmdd.p`,
    the title being `Gutil yyyymmdd.p (month year)`, and the corresponding
    release notes (can be auto-generated).
    *   The release archive must be added to the Github release for the Bazel
        Central Registry to achieve
        [archive checksum stability](https://blog.bazel.build/2023/02/15/github-archive-checksum.html)
    *   The release archive can be added after creating a release. Download the
        source zip and re-uploading it as the stable release archive.
4.  The
    [Bazel Central Registry for Gutil](https://github.com/bazelbuild/bazel-central-registry/tree/main/modules/gutil)
    must also be updated accordingly by following the
    [contribution guidelines](https://github.com/bazelbuild/bazel-central-registry/blob/main/docs/README.md).
