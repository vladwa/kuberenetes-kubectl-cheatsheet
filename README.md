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

#### Replica Sets (rs) 

| Description | **kubectl command** | 

