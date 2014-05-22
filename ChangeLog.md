ChangeLog
=========

v4
--

Packages:

- consul-ui - now looks pretty; pre-compiles static assets

v3
--

Server Deployment:

- two-staged boot - bootstrap -> cluster (see README)
- uses latest available stemcell; uploads latest public stemcell if none available

Client Usage:

- `consul_ctl reload` available for client usage to reload all local .json config
- set recursor to 8.8.8.8 if BOSH not providing DNS

Packages:

- consul v0.2.1
- added [envconsul](https://github.com/hashicorp/envconsul) v0.1

Development:

- [confd] bin/submodule helper to add submodules into $GOPATH
- [confd] possible to build confd package from source via manually modifying `packages/confd/packaging`

v2
--

All:

- bind DNS to port 53

v1
--

Packages:

- consul v0.2.0
- consul-ui
- confd v0.4.0-beta2
