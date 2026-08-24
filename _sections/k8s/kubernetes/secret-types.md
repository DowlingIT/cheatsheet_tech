---
title: Secret Types & Options
subtopic: kubernetes
group: Configuration
order: 3
---

#### Common secret types

```bash
kubectl create secret docker-registry regcred \
  --docker-server=registry.example.com --docker-username=me --docker-password=pw

kubectl create secret tls my-tls --cert=tls.crt --key=tls.key
```

```
Opaque                       arbitrary key/value data (the default)
kubernetes.io/dockerconfigjson  pull secret, referenced via imagePullSecrets
kubernetes.io/tls               cert + key pair, used by Ingress TLS
kubernetes.io/service-account-token  auto-mounted into every pod
```

#### Locking a ConfigMap/Secret against edits

```yaml
data: { LOG_LEVEL: debug }
immutable: true    # rejects updates — forces a new object + rollout instead
```
