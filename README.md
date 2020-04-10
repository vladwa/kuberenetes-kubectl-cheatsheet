#### cka-ckad-prep-notes

Master and Worker nodes ports 
![alt text](ports.png)

#### You can create the following resources using kubectl run with the --generator flag

| **Resource**  | **api group** | **kubectl command** |
| ------------- | ------------- | ------- |
| Pod  | v1  | `kubectl run --generator=run-pod/v1` |
| Replication controller (deprecated)  | v1 | `kubectl run --generator=run/v1` |
| Deployment (deprecated) | apps/v1beta1 | `kubectl run --generator=deployment/apps.v1beta1` |
| Job (deprecated) | batch/v1 | `kubectl run --generator=job/v1` |
| CronJob (deprecated) | batch/v1beta1 | `kubectl run --generator=cronjob/v1beta1` |
| CronJob (deprecated) | batch/v2alpha1 | `kubectl run --generator=cronjob/v2alpha1` |

### Pod 
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `pods`  | `po`  | -  | `true` | `Pod` | `[create delete deletecollection get list patch update watch]`

| Describtion | kubectl command |
| ------------- | ------------- |
| Create | `kubectl run nginx --generator=run-pod/v1 --image=nginx`|
| Create in particular namespace | `kubectl run nginx --generator=run-pod/v1 --image=nginx -n NAMEPSPACE` |
| Dry run,print object without creating it | `kubectl run POD_NAME --generator=run-pod/v1 --image=nginx --dry-run -o yaml` |
| Create from File | `kubectl create -f pod.yaml` |
| Create from File in particular namespace |  `kubectl create -f pod.yaml -n NAMEPSPACE` |
| List | `kubectl get po` or `kubectl get pod` or `kubectl get pods` |
| List in all namespaces | `kubectl get pods --all-namespaces` or `kubectl get pods -A` |
| List with more information | `kubectl get pods -owide` |
| List information in custom columns | `kubectl get pod POD_NAME -o custom-columns=CONTAINER:.spec.containers[0].name,IMAGE:.spec.containers[0].image` |
| Verbose Debug information | `kubectl describe pod POD_NAME` |
| Logs | `kubectl logs POD_NAME` |
| Logs (multi-container case) | `kubectl logs POD_NAME -c CONTAINER_NAME` |
| Tail logs | `kubectl logs -f POD_NAME` | 
| Tail logs (multi-container case) | `kubectl logs -f POD_NAME -c CONTAINER_NAME` | 
| Delete | `kubectl delete pod POD_NAME` or `kubectl delete -f pod.yaml` or `kubectl delete pod/POD_NAME` |
| Delete in particular namespace | `kubectl delete pod POD_NAME -n NAMESPACE` |
| Get  | `kubectl get pod POD_NAME` |
| Watch  | `kubectl get pod POD_NAME --watch` |
| Patch | `kubectl patch pod valid-pod -p '{"spec":{"containers":[{"name":"kubernetes-serve-hostname"}]}}'` |
| Create and wrtie its spec to file | `kubectl run POD_NAME --image=nginx --restart=Never --dry-run -o yaml > pod.yaml`
| List in Json output format | `kubectl get pods -o json` |
| List in YAML output format | `kubectl get pods -o yaml` |
| Run command in existing | `kubectl exec POD_NAME -- ls /` |
| Run command in existing pod (multi-container case) | `kubectl exec POD_NAME -c CONTAINER_NAME -- ls /` |

### ReplicaSet 
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `replicasets`  | `rs`  | `apps`,`extensions` | `true` | `ReplicaSet` | `[create delete deletecollection get list patch update watch]`

| Describtion | kubectl command |
| ------------- | ------------- |
| create | `kubectl create -f replicaset.yaml`|
| List | `kubectl get rs` or `kubectl get replicaset` or `kubectl get replicasets` |
| List in all namespaces | `kubectl get rs --all-namespaces` or `kubectl get rs -A` |
| Delete | `kubectl delete rs REPLICASET_NAME` or `kubectl delete -f replicaset.yaml`|
| Get | `kubectl get rs REPLICASET_NAME` |

### Deployment
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `deployments`  | `deploy`  | `apps`,`extensions` | `true` | `Deployment` | `[create delete deletecollection get list patch update watch]`

### DaemonSet
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `daemonsets`  | `ds`  | `apps`,`extensions` | `true` | `DaemonSet` | `[create delete deletecollection get list patch update watch]`

### CronJob
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `cronjobs`  | `cj`  | `batch` | `true` | `CronJob` | `[create delete deletecollection get list patch update watch]`

### Job
| NAME  | SHORTNAMES | APIGROUP | NAMESPACED | KIND | VERBS |
| ------------- | ------------- | ------- | -------- | --------- | -------- |
| `jobs`  | `cj`  | `batch` | `true` | `Job` | `[create delete deletecollection get list patch update watch]`

