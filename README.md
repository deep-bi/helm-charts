# Deep.BI Helm Charts

Helm charts for the [Deep.BI](https://www.deep.bi/) builds of the Apache Druid and StarRocks Kubernetes operators, served from `https://charts.deep.bi`.

```bash
helm repo add deep-bi https://charts.deep.bi
helm repo update
```

## Charts hosted

### Druid Operator

Source: [deep-bi/druid-operator](https://github.com/deep-bi/druid-operator). About the operator: [Tools for Apache Druid](https://www.deep.bi/apache-druid/tools#operator).

| Chart | Description |
|---|---|
| `druid-operator` | Deep.BI Druid Operator |

```bash
helm install druid-operator deep-bi/druid-operator -n druid-operator --create-namespace
```

### StarRocks Operator

Source: [deep-bi/starrocks-kubernetes-operator](https://github.com/deep-bi/starrocks-kubernetes-operator). About the operator: [StarRocks Kubernetes operator](https://www.deep.bi/starrocks/kubernetes-operator).

| Chart | Description |
|---|---|
| `kube-starrocks` | The operator and a StarRocks cluster together |
| `operator` | The Deep.BI StarRocks Operator only |
| `starrocks` | A StarRocks cluster only (needs the operator) |
| `warehouse` | A StarRocks warehouse (needs the operator) |

```bash
helm install starrocks-operator deep-bi/operator --version 1.11.8-deepbi.4 -n starrocks --create-namespace
```

The StarRocks charts keep the upstream chart names. Their versions carry a `-deepbi.N` suffix, which Helm treats as a
pre-release, so always pass `--version`. To list them:

```bash
helm search repo deep-bi --devel --versions
```
