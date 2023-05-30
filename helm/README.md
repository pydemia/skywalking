# Helm

## Install

```bash
SKYWALKING_RELEASE_VERSION=4.3.0  # change the release version according to your need
SKYWALKING_RELEASE_NAME=skywalking  # change the release name according to your scenario
SKYWALKING_RELEASE_NAMESPACE=default  # change the namespace to where you want to install SkyWalking

helm pull \
  oci://registry-1.docker.io/apache/skywalking-helm \
  --version "${SKYWALKING_RELEASE_VERSION}" \
  --untar

helm install "${SKYWALKING_RELEASE_NAME}" \
  oci://registry-1.docker.io/apache/skywalking-helm \
  --version "${SKYWALKING_RELEASE_VERSION}" \
  -n "${SKYWALKING_RELEASE_NAMESPACE}" \
  --set oap.image.tag=9.2.0 \
  --set oap.storageType=elasticsearch \
  --set ui.image.tag=9.2.0
```

