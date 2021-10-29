# copier

Replicates all `Secrets` in the `copier` namespace that have label `copier` set to `'true'` to all other namespaces in given cluster. It's just a mildly modifed [example](https://github.com/flant/shell-operator/tree/master/examples/104-secret-copier) from [shell-operator](https://github.com/flant/shell-operator), therefore all credit belongs to the authors of the original.


## Difference from [104-secret-copier](https://github.com/flant/shell-operator/tree/master/examples/104-secret-copier)

* doesn't need a custom container image (better for clusters without a private registry)
* easily deployable as a [Kustomize remote base/build](https://github.com/kubernetes-sigs/kustomize/blob/master/examples/remoteBuild.md)
* deployed as `Deployment` instead of just a `Pod`, therefore doesn't die when `Pod` is rescheduled
* different label and namespace name (`secret-copier` -> `copier`)
