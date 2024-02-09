# istio-bookinfo-app

```bash
gitpod /workspace/istio-bookinfo-app (main) $ k get ns
NAME              STATUS   AGE
default           Active   3d10h
kube-node-lease   Active   3d10h
kube-public       Active   3d10h
kube-system       Active   3d10h
gitpod /workspace/istio-bookinfo-app (main) $ k create ns bookinfo-app
namespace/bookinfo-app created
gitpod /workspace/istio-bookinfo-app (main) $ k apply -f bookinfo.yaml -n bookinfo-app
service/details created
serviceaccount/bookinfo-details created
deployment.apps/details-v1 created
service/ratings created
serviceaccount/bookinfo-ratings created
deployment.apps/ratings-v1 created
service/reviews created
serviceaccount/bookinfo-reviews created
deployment.apps/reviews-v1 created
deployment.apps/reviews-v2 created
deployment.apps/reviews-v3 created
service/productpage created
serviceaccount/bookinfo-productpage created
deployment.apps/productpage-v1 created
gitpod /workspace/istio-bookinfo-app (main) $ k get all -A -n bookinfo-app
NAMESPACE      NAME                                   READY   STATUS    RESTARTS   AGE
bookinfo-app   pod/details-v1-698d88b-dhbnv           1/1     Running   0          25s
bookinfo-app   pod/productpage-v1-675fc69cf-j64mh     1/1     Running   0          19s
bookinfo-app   pod/ratings-v1-6484c4d9bb-d27n5        1/1     Running   0          23s
bookinfo-app   pod/reviews-v1-5b5d6494f4-985hp        1/1     Running   0          22s
bookinfo-app   pod/reviews-v2-5b667bcbf8-v6g5j        1/1     Running   0          21s
bookinfo-app   pod/reviews-v3-5b9bd44f4-4b9wp         1/1     Running   0          21s
kube-system    pod/cilium-2jz5x                       1/1     Running   0          3d10h
kube-system    pod/cilium-8rppp                       1/1     Running   0          3d10h
kube-system    pod/cilium-operator-64c5f659f5-rh4kd   1/1     Running   0          3d10h
kube-system    pod/cilium-xwv82                       1/1     Running   0          3d10h
kube-system    pod/coredns-6857f5494d-hpgzp           1/1     Running   0          3d10h
kube-system    pod/coredns-6857f5494d-lghqg           1/1     Running   0          3d10h
kube-system    pod/cpc-bridge-proxy-n4dzg             1/1     Running   0          3d10h
kube-system    pod/cpc-bridge-proxy-rshjf             1/1     Running   0          3d10h
kube-system    pod/cpc-bridge-proxy-sxlvq             1/1     Running   0          3d10h
kube-system    pod/csi-do-node-86nrf                  2/2     Running   0          3d10h
kube-system    pod/csi-do-node-b9hvb                  2/2     Running   0          3d10h
kube-system    pod/csi-do-node-fdd9t                  2/2     Running   0          3d10h
kube-system    pod/do-node-agent-27kmm                1/1     Running   0          3d10h
kube-system    pod/do-node-agent-4k8xx                1/1     Running   0          3d10h
kube-system    pod/do-node-agent-dd6vd                1/1     Running   0          3d10h
kube-system    pod/hubble-relay-bf78b8584-82v2t       1/1     Running   0          3d10h
kube-system    pod/hubble-ui-dd784fb98-t8w9b          2/2     Running   0          3d10h
kube-system    pod/konnectivity-agent-g6mwf           1/1     Running   0          3d10h
kube-system    pod/konnectivity-agent-sqm5z           1/1     Running   0          3d10h
kube-system    pod/konnectivity-agent-wvgsj           1/1     Running   0          3d10h
kube-system    pod/kube-proxy-ghkbn                   1/1     Running   0          3d10h
kube-system    pod/kube-proxy-rfqc6                   1/1     Running   0          3d10h
kube-system    pod/kube-proxy-vbkjn                   1/1     Running   0          3d10h

NAMESPACE      NAME                   TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)                  AGE
bookinfo-app   service/details        ClusterIP   10.245.53.236    <none>        9080/TCP                 27s
bookinfo-app   service/productpage    ClusterIP   10.245.42.109    <none>        9080/TCP                 21s
bookinfo-app   service/ratings        ClusterIP   10.245.65.222    <none>        9080/TCP                 25s
bookinfo-app   service/reviews        ClusterIP   10.245.152.76    <none>        9080/TCP                 24s
default        service/kubernetes     ClusterIP   10.245.0.1       <none>        443/TCP                  3d10h
kube-system    service/hubble-peer    ClusterIP   10.245.7.226     <none>        443/TCP                  3d10h
kube-system    service/hubble-relay   ClusterIP   10.245.90.171    <none>        80/TCP                   3d10h
kube-system    service/hubble-ui      ClusterIP   10.245.118.119   <none>        80/TCP                   3d10h
kube-system    service/kube-dns       ClusterIP   10.245.0.10      <none>        53/UDP,53/TCP,9153/TCP   3d10h

NAMESPACE     NAME                                DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR            AGE
kube-system   daemonset.apps/cilium               3         3         3       3            3           kubernetes.io/os=linux   3d10h
kube-system   daemonset.apps/cpc-bridge-proxy     3         3         3       3            3           <none>                   3d10h
kube-system   daemonset.apps/csi-do-node          3         3         3       3            3           <none>                   3d10h
kube-system   daemonset.apps/do-node-agent        3         3         3       3            3           kubernetes.io/os=linux   3d10h
kube-system   daemonset.apps/konnectivity-agent   3         3         3       3            3           <none>                   3d10h
kube-system   daemonset.apps/kube-proxy           3         3         3       3            3           <none>                   3d10h

NAMESPACE      NAME                              READY   UP-TO-DATE   AVAILABLE   AGE
bookinfo-app   deployment.apps/details-v1        1/1     1            1           26s
bookinfo-app   deployment.apps/productpage-v1    1/1     1            1           20s
bookinfo-app   deployment.apps/ratings-v1        1/1     1            1           24s
bookinfo-app   deployment.apps/reviews-v1        1/1     1            1           23s
bookinfo-app   deployment.apps/reviews-v2        1/1     1            1           22s
bookinfo-app   deployment.apps/reviews-v3        1/1     1            1           22s
kube-system    deployment.apps/cilium-operator   1/1     1            1           3d10h
kube-system    deployment.apps/coredns           2/2     2            2           3d10h
kube-system    deployment.apps/hubble-relay      1/1     1            1           3d10h
kube-system    deployment.apps/hubble-ui         1/1     1            1           3d10h

NAMESPACE      NAME                                         DESIRED   CURRENT   READY   AGE
bookinfo-app   replicaset.apps/details-v1-698d88b           1         1         1       27s
bookinfo-app   replicaset.apps/productpage-v1-675fc69cf     1         1         1       21s
bookinfo-app   replicaset.apps/ratings-v1-6484c4d9bb        1         1         1       25s
bookinfo-app   replicaset.apps/reviews-v1-5b5d6494f4        1         1         1       24s
bookinfo-app   replicaset.apps/reviews-v2-5b667bcbf8        1         1         1       23s
bookinfo-app   replicaset.apps/reviews-v3-5b9bd44f4         1         1         1       23s
kube-system    replicaset.apps/cilium-operator-64c5f659f5   1         1         1       3d10h
kube-system    replicaset.apps/coredns-6857f5494d           2         2         2       3d10h
kube-system    replicaset.apps/hubble-relay-bf78b8584       1         1         1       3d10h
kube-system    replicaset.apps/hubble-ui-dd784fb98          1         1         1       3d10h
gitpod /workspace/istio-bookinfo-app (main) $ 
```