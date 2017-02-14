# DFC-documentation repository

This repository acts as an easy path for all the documentation related to the Dragon Fire Card projects. You may also find documentation in the project's repository itself.

# Uploading Large Files

Repositories allow commits up to 100MB per file. For large binary files, releases is the best option. On this way, a repository contains the project's code, and releases contains the binaries available for download. This also helps to keep track of different binary versions.

But even in releases, you need to split the binaries in up to 2048MB parts.

To split the file in 2GB parts:

dd if=bigfile of=file1 count=2048 bs=1M
dd if=bigfile skip=2048 of=file2 count=2048 bs=1M
dd if=bigfile skip=4096 of=file3 count=2048 bs=1M
...

To rebuild the file:

cat file1 > bigfile
cat file2 >> bigfile
cat file3 >> bigfile
...

For further details about large binaries in github:

https://help.github.com/articles/distributing-large-binaries/

For an example of releases with binaries:

https://github.com/DFC-OpenSource/ox-ctrl/releases

You can create a release under 'Releases' > 'Create a new release' in the repository. It will include automatically the tar.gz with the code. You will also have an option to include large binary files. If you don't have any file in the repository, create a README.md explaining the repository. A hint is organizing the releases with tags like v1.0, v1.1, ... it is up to you.
