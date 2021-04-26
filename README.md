# Simple Helm chart for Hadoop 3

## Prerequisites

Retrieve and build hadoop3:latest from https://github.com/Chester-Ong/hadoop3

## How-to

**Install as a subchart**

```bash
$ cd <YOUR MAIN HELM-CHART>
$ cd charts
# This clones the chart as directory hadoop
$ git clone https://github.com/Chester-Ong/helm-hadoop hadoop
```

**Edit your main &lt;MAIN HELM-CHART&gt;/values.yaml**

```
In values.yaml file

 ...
 ...
 ...
 
# Change any settings here to override in charts/hadoop/values.yaml
hadoop:
  enabled: true
  replicaCount: 1
  nameOverride: ""
  fullnameOverride: ""
  image:
    repository: hadoop3
    pullPolicy: IfNotPresent
    # Overrides the image tag whose default is the chart appVersion.
    tag: "latest"
  nodeSelector: {}
  service:
    nodeManagerPort: 8042
    resourceManagerPort: 8088
    nameNodePort: 9870
    dataNodePort: 9864
    jobHistoryPort: 19888
```