# Fixes

- specify absolute path to consule binary in ctl. When combining consul with shield the shield-plugin named `consul` was shadowing the real binary. This fixes that issue allowing shield and consul to be colocated.
