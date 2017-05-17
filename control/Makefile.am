# Makefile.am for yast2-installation-control/control
#

control_DATA = \
       control.rnc \
       control.rng \
       partitioning_elements.rnc \
       partitioning_elements.rng

# Distribute also the generated control.rng file, the reason is that "trang"
# is a Java tool which adds huge dependency in OBS.
#
# The conversion needs to be done manually (by running "make")
# and the converted RNG file must be committed to Git.
#
# At build time the RNG file from tarball will have a newer time stamp
# and thus it will not need rebuild/update making "trang" unnecessary.
EXTRA_DIST = $(control_DATA)

include $(top_srcdir)/Makefile.am.common

control.rng: control.rnc
	trang -I rnc -O rng control.rnc control.rng

