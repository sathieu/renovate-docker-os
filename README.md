# OS changed while updating a docker image

When using an image with digest pointing to a specific architecture and os, renovate ensure the same architecture but can use another OS.

For example, this image:

```
registry.k8s.io/csi-vsphere/driver:v3.3.1@sha256:5ef2f153813565d41a41c0700d1917c077f30bbbe735fd3f9e9ba18956d65bed
```

which is `os=linux` `architecture=amd64`

## Current behavior

Image is updated to:

```
registry.k8s.io/csi-vsphere/driver:v3.3.1@sha256:9245b0dbe11af8a90080e2d59a0e488bc6272b20d50eab3f643967c3d117a957
```

which is `os=windows` `architecture=amd64`

## Expected behavior

Like for arcvhitecture, os should not be changed.

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.

Production repo commit: https://gitlab.com/kubitus-project/kubitus-installer/-/commit/627599740756f69f46458aebc40c53d176f66c52?merge_request_iid=3550
