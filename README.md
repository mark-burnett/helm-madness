# Overview
Just kicking around ideas to avoid escaping gotpl for Prometheus configuration.

```bash
$ helm install --dry-run --debug . -n foo
[debug] Created tunnel using local port: '50825'

[debug] SERVER: "localhost:50825"

[debug] Original chart version: ""
[debug] CHART PATH: /Users/mburnett/tmp/helmfile/foo

NAME:   foo
REVISION: 1
RELEASED: Wed May 24 19:47:26 2017
CHART: foo-0.1.0
USER-SUPPLIED VALUES:
{}

COMPUTED VALUES:
"false": data

HOOKS:
MANIFEST:

---
# Source: foo/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: rules
data:
  plan-file.yaml: |
    nothing:
      fish:
        y: here
  tricky-file.yaml: |
    something:
      might:
        b: {{ .Values.does_not_exist | required }}

```
