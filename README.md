# Driver for rtl88x2bu wifi adaptors

Updated driver for rtl88x2bu wifi adaptors based on
rtl88x2BU_WiFi_linux_v5.3.1_27678.20180430_COEX20180427-5959 originally
downloaded from [D-Link's download page for the DWA-182 Rev
D](https://support.dlink.com/ProductInfo.aspx?m=DWA-182).


## Purpose of the repository

The purpose of this repository is to update the driver such that it can be
compiled with recent versions of the Linux kernel on x86-64. The repository
of [cylinx](https://github.com/cilynx/rtl88x2BU_WiFi_linux_v5.3.1_27678.20180430_COEX20180427-5959)
does something very similar.

The main difference between this and cylinx' repositories are that this
repository compiles with -O2 (and can compile with -O3), leading to few
additional bugfixes and possibly some performance improvements. On the other
hand, cylinx' repository seems to support some RasperryPi use cases.

## Simple Usage

In order to make direct use of the driver it should suffice to build the driver
with `make` and to load it with `insmod 88x2bu.ko`. This will allow you
to use the driver directly without changing your system persistently.

## DKMS installation

If you want to have the driver available at startup, it will you convenient to
register it in DKMS. This can be done completely automatically with the script
`deploy.sh`.
