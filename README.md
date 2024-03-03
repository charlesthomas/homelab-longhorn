# homelab-longhorn

This is a mirco-services repo for deploying
[longhorn](https://longhorn.io)
into [my homelab](https://github.com/charlesthomas/homelab).

## disabling usage metrics

1. open UI
1. go to Settings -> General
1. uncheck Allow Collecting Longhorn Usage Metrics
1. click Save

there's [an open GitHub Issue](https://github.com/longhorn/longhorn/issues/7050) to add this to the chart

## uninstallation

longhorn blocks its own uninstallation, so you don't lose data

this is very good since the helm chart seems to generate a deletion job for some reason, which fails; meaning it's dumb but safe

to do it anyway:

```bash
kubectl -n longhorn edit settings.longhorn.io deleting-confirmation-flag
```

---
This repo is templated via
[homelab-template](https://github.com/charlesthomas/homelab-template)
and automatically updated via
[🤖 Templatron](https://github.com/charlesthomas/templatron).
