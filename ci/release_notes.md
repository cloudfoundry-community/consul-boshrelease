# Improvements

- The BOSH2 manifests for deploying this release are better now.

- New `consul.http_local` parameter alllows Consul to use HTTP
  locally, even if TLS certificates are in use publicly.

- You can now configure WAN servers for a LAN/WAN topology, via
  the new `consul.wan_servers` property.
