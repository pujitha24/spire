# Supported Integrations

SPIRE Server and Agent integrate with various software and platforms. The
following sections detail the official project support stance for these
integrations. Usually this means that we actively test the integration with the
listed versions (though not always; sometimes we rely on support declarations
of client libraries used by the integrations). If an integration is not
represented, it does not mean that the integration is not supported but that
there is no official stance.

## Envoy

The SPIRE project officially tests integrations against the latest five minor
versions of Envoy, starting with v1.13 (the earliest build with the v3 API).

Envoy v2 API support is deprecated and as such we only actively test against
the last minor version that supports it (v1.16).

## Kubernetes

The SPIRE project aims to support the Kubernetes versions that are currently
supported upstream (generally the three most recent minor releases). We will
not require Kubernetes features that are not available across all of these
versions.

The most recent Kubernetes feature that SPIRE relies on is [projected service
account tokens][psat], which have been available since Kubernetes 1.20. Later
versions are expected to work as well.

Integration tests are run against a range of Kubernetes versions on a
best-effort basis. The minimum version exercised by CI is defined in
[`integration_k8s_min_version.txt`](../test/integration/suites/k8s/integration_k8s_min_version.txt).

For production deployments we recommend using the [SPIRE Helm charts][helm]
rather than the static manifests referenced in the quickstart guides.

[psat]: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/#service-account-token-volume-projection
[helm]: https://github.com/spiffe/helm-charts-hardened
