When you working multiple gcloud account

sometimes when you've change another account then want access kubernetes will showing forbidden message like this

```bash
Error from server (Forbidden): pods is forbidden: User "<email>" cannot list pods in the namespace "<namespace>": No policy matched.
Required "container.pods.list" permission.
```

To fixing it

```bash
$ gcloud init
$ gcloud container clusters list
$ gcloud container clusters get-credentials <cluster-name> --zone <zone>
```

details :
 - https://www.attosol.com/working-with-multiple-gcp-configurations-kubernetes-clusters-from-command-line/
