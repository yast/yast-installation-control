# YaST - The Control File Schema Definition #

[[![Workflow Status](https://github.com/yast/yast-installation-control/workflows/CI/badge.svg?branch=master)](
https://github.com/yast/yast-installation-control/actions?query=branch%3Amaster)
[![Jenkins Status](https://ci.opensuse.org/buildStatus/icon?job=yast-yast-installation-control-master)](
https://ci.opensuse.org/view/Yast/job/yast-yast-installation-control-master/)

## Notes

Distribute also the generated control.rng file, the reason is that "trang"
is a Java tool which adds huge dependency in OBS.

The conversion needs to be done manually (by running "rake generate_rng")
and the converted RNG file must be committed to Git.

At build time the RNG file from tarball will have a newer time stamp
and thus it will not need rebuild/update making "trang" unnecessary.

See also the [documentation for the control file][doc].

[doc]: https://github.com/yast/yast-installation/blob/master/doc/control-file.md
