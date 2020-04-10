# cka-ckad-prep-notes

Master and Worker nodes ports 
![alt text](ports.png)

You can create the following resources using kubectl run with the --generator flag

| **Resource**  | **api group** | **kubectl command** |
| ------------- | ------------- |
| Pod  | v1  | kubectl run --generator=run-pod/v1 |
| Replication controller (deprecated)  | v1 | kubectl run --generator=run/v1 |
