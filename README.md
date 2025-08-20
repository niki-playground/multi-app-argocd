# Argo CD examples: App-of-Apps and ApplicationSet (OpenShift-friendly)

## Quick Start

```bash
ARGO_NS=openshift-gitops
TARGET_NS=my-team-namespace

# Create workload namespace (if not present)
oc new-project $TARGET_NS || true
```

Push this folder to a Git repo (replace https://your.git.example/repo.git in yaml files with your actual repo URL).

## A) App-of-Apps

Apply the root app (it will create child Applications):

```bash
oc apply -n $ARGO_NS -f root-app.yaml
```

## B) ApplicationSet

Apply the ApplicationSet (it will generate child Applications using the list):

```bash
oc apply -n $ARGO_NS -f appset/appset.yaml
```

Open Argo CD UI to watch sync/health.
