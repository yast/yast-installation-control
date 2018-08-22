# YaST - The Control File Schema Definition #

[![Travis Build](https://travis-ci.org/yast/yast-installation-control.svg?branch=master)](https://travis-ci.org/yast/yast-installation-control)
[![Jenkins Build](http://img.shields.io/jenkins/s/https/ci.opensuse.org/yast-installation-control-master.svg)](https://ci.opensuse.org/view/Yast/job/yast-installation-control-master/)

## Notes

Distribute also the generated control.rng file, the reason is that "trang"
is a Java tool which adds huge dependency in OBS.

The conversion needs to be done manually (by running "rake regenerate_rng")
and the converted RNG file must be committed to Git.

At build time the RNG file from tarball will have a newer time stamp
and thus it will not need rebuild/update making "trang" unnecessary.

See also the [documentation for the control file][doc].

[doc]: https://github.com/yast/yast-installation/blob/master/doc/control-file.md
