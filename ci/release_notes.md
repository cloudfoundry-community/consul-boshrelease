# features
- updated consul to v0.8.4
- exporting ssl_ca, ssl_cert, ssl_key via bosh links for other jobs / deployments to pick up

# fixes
- removed redundant ui-dir setting. The webui is now bundled in the consul binary and can be served directly with the `-ui` option.
