# Crossplane configuration for "CloudSQL as a Service"

This repository contains the definition for a [Crossplane configuration](https://docs.crossplane.io/v1.11/concepts/packages/#configuration-packages) that bundles a set of API definitions. This configuration is a starting point for new users who are creating their first control plane in [Upbound](https://cloud.upbound.io).

When this configuration is installed on a control plane, the control plane will have APIs to provision fully configured Google Cloud Platform (GCP) CloudSQL instances, composed using cloud service primitives from the [Upbound Official GCP Provider](https://marketplace.upbound.io/providers/upbound/provider-gcp).

## What's Inside

A custom API in [Crossplane](https://docs.crossplane.io/v1.11/getting-started/introduction/) is defined by:

- a CompositeResourceDefinition (XRD). This defines the schema or shape of the API.
- A Composition(s). Compositions implement the schema by _composing_ a set of Crossplane managed resources together.

For this configuration, the CloudSQL API is defined by:

- a [PostgreSQLInstance](/apis/definition.yaml) type
- the PostgreSQLInstance is [composed](/apis/composition.yaml) of a single DBInstance resource.

This repository also contains an [example claim](/.up/examples/postgresql.yaml). You can apply this file on your control plane to invoke the CloudSQL API and cause a database to be created.

## Next Steps

This repository is a starting point. You should be feel encouraged to:

1) create new API definitions in this same repo
2) tweak the existing API definition for CloudSQL to your needs

Upbound will automatically detect the commits you make in your repo and build the configuration package for you. To learn more about how to build APIs for your managed control planes in Upbound, read the guide on [Upbound's docs](https://docs.upbound.io).
