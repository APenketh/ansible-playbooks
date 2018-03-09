ansible-swapfile
================

Cloned From Original Location: https://github.com/kamaln7/ansible-swapfile

This role configures a swapfile (/swapfile) with the (default) size of 512MB.

## Variables

* `swapfile_use_dd` [default: `True`]: if set to False, `fallocate` is used to create the swapfile, otherwise, `dd` is used. Some systems will not support `fallocate` which is why two options are given.

* `swapfile_size` [default: `1024`]: `swapfile_size` must be set to the amount of megabytes to write, e.g. `512`.

    If `swapfile_use_dd` is set to False, `swapfile_size` must be set to the size of the swapfile to create in the format that `fallocate` expects (Example: 512MB):

    The  length and offset arguments may be followed by binary (2^N) suffixes KiB, MiB, GiB, TiB, PiB and EiB (the "iB" is optional, e.g. "K" has the same meaning as "KiB") or decimal (10^N) suffixes KB, MB, GB, PB and EB.

* `swapfile_location` [default: `/swapfile`]: the location of where the swapfile will be created

### Optional

The following variables are set to `False` by default and will not have any effect on your hosts. Setting them to any value other than `False` will update your hosts' sysctl.conf file.

* `swapfile_swappiness` [default: `False`]: the swappiness percentage (vm.swappiness) -- the lower it is, the less your system swaps memory pages

* `swapfile_vfs_cache_pressure` [default: `False`]: "this percentage value controls the tendency of the kernel to reclaim the memory which is used for caching of directory and inode objects."
