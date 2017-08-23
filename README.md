# Deploy Consul to BOSH

Hashicorp [Consul](https://www.consul.io/) makes it simple for services to register themselves and to discover other services via a DNS or HTTP interface. It also offers flexible key/value storage.

One of the fastest ways to get [consul](https://www.consul.io/) running on any infrastructure is to deploy this BOSH release.

* Discussions and CI notifications at [#consul-boshrelease channel](https://cloudfoundry.slack.com/messages/C6SUUTMDJ/) on https://slack.cloudfoundry.org

## Usage

To use this bosh release, first upload it to your bosh:

```
export BOSH_ENVIRONMENT=<alias>
export BOSH_DEPLOYMENT=consul

git clone https://github.com/cloudfoundry-community/consul-boshrelease.git
cd consul-boshrelease
bosh deploy manifests/consul.yml -o manifests/operators/firsttime.yml
```

The `consul.yml` manifest is deliberately missing the required `update:` section of the manifest. This is to ensure that you - the operator - choose the correct `update:` section - either `firsttime.yml` for the first deployment (deploy all instances at the same time so they form a cluster) or `existing.yml` for all subsequent deployments (rolling updates).

If you get the following error then you have forgotten to provide either of these two operator files:

```
Task 1045 | 23:24:04 | Preparing deployment: Preparing deployment (00:00:00)
                     L Error: Required property 'update' was not specified in object ({"instance_groups"=>[{"azs"=>["z1", "z2", "z3"], "instances"=>3, "jobs"=>...
```

### Subsequent deploys/upgrades

Replace `manifests/operators/firsttime.yml` above with `manifests/operators/existing.yml` so that each instance is updated one at a time:

```
bosh deploy manifests/consul.yml -o manifests/operators/existing.yml
```
