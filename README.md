# hello-world-minikube

```
> minikube start
ð  Microsoft Windows 10 Home 10.0.19044 Build 19044 ä¸ã® minikube v1.25.2
â¨  docker ãã©ã¤ãã¼ãèªåçã«é¸æããã¾ãããä»ã®é¸æè¢: virtualbox, ssh
ð  minikube ã¯ã©ã¹ã¿ã¼ä¸­ã®ã³ã³ãã­ã¼ã«ãã¬ã¼ã³ã® minikube ãã¼ããèµ·åãã¦ãã¾ã
ð  ãã¼ã¹ã¤ã¡ã¼ã¸ãåå¾ãã¦ãã¾ã...
ð¾  Kubernetes v1.23.3 ã®ãã¦ã³ã­ã¼ãã®æºåããã¦ãã¾ã
    > preloaded-images-k8s-v17-v1...: 505.68 MiB / 505.68 MiB  100.00% 28.87 Mi
    > gcr.io/k8s-minikube/kicbase: 379.06 MiB / 379.06 MiB  100.00% 9.28 MiB p/
ð¥  docker container (CPUs=2, Memory=3500MB) ãä½æãã¦ãã¾ã.../ E0524 23:36:30.942608   18836 kic.go:267] icacls failed applying permissions - err - [%!s(<nil>)], output - [ï¿½ï¿½ï¿½ï¿½ï¿½tï¿½@ï¿½Cï¿½ï¿½: C:\Users\yuto2\.minikube\machines\minikube\id_rsa
1 ï¿½Ìtï¿½@ï¿½Cï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½Éï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½Üï¿½ï¿½ï¿½ï¿½B0 ï¿½Ìtï¿½@ï¿½Cï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½ï¿½Åï¿½ï¿½Üï¿½ï¿½ï¿½ï¿½Åï¿½ï¿½ï¿½]

ð³  Docker 20.10.12 ã§ Kubernetes v1.23.3 ãæºåãã¦ãã¾ã...
    âª kubelet.housekeeping-interval=5m
    âª è¨¼ææ¸ã¨éµãä½æãã¦ãã¾ã...
    âª ã³ã³ãã­ã¼ã«ãã¬ã¼ã³ãèµ·åãã¦ãã¾ã...
    âª RBAC ã®ã«ã¼ã«ãè¨­å®ä¸­ã§ã...
ð  Kubernetes ã³ã³ãã¼ãã³ããæ¤è¨¼ãã¦ãã¾ã...
    âª gcr.io/k8s-minikube/storage-provisioner:v5 ã¤ã¡ã¼ã¸ãä½¿ç¨ãã¦ãã¾ã
ð  æå¹ãªã¢ããªã³: storage-provisioner, default-storageclass

â  C:\Program Files\Docker\Docker\resources\bin\kubectl.exe ã®ãã¼ã¸ã§ã³ã¯ 1.21.3 ã§ãKubernetes 1.23.3 ã¨äºææ§ã ãªãããããã¾ããã
    âª kubectl v1.23.3 ãå¿è¦ã§ããï¼ 'minikube kubectl -- get pods -A' ãè©¦ãã¦ã¿ã¦ãã ãã
ð  å®äºãã¾ããï¼ kubectl ãã"minikube"ãã¯ã©ã¹ã¿ã¨ã"default"ããã¼ã ã¹ãã¼ã¹ãä½¿ç¨ããããæ§æããã¾ãã
```

```
> minikube dashboard
```
![image](https://user-images.githubusercontent.com/55943803/170067275-26ae2ca1-6e6c-4226-8216-de084b82fb26.png)


```
> kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4
deployment.apps/hello-minikube created
```

```
> kubectl get deployments
NAME             READY   UP-TO-DATE   AVAILABLE   AGE
hello-minikube   1/1     1            1           6m17s
```

```
> kubectl get pods
NAME                              READY   STATUS    RESTARTS   AGE
hello-minikube-7bc9d7884c-6xz8q   1/1     Running   0          7m31s
```

```
> kubectl get events
LAST SEEN   TYPE      REASON                                             OBJECT                                 MESSAGE
8m12s       Normal    Scheduled                                          pod/hello-minikube-7bc9d7884c-6xz8q    Successfully assigned default/hello-minikube-7bc9d7884c-6xz8q to minikube
8m11s       Normal    Pulling                                            pod/hello-minikube-7bc9d7884c-6xz8q    Pulling image "k8s.gcr.io/echoserver:1.4"
7m59s       Normal    Pulled                                             pod/hello-minikube-7bc9d7884c-6xz8q    Successfully pulled image "k8s.gcr.io/echoserver:1.4" in 11.979392s
7m59s       Normal    Created                                            pod/hello-minikube-7bc9d7884c-6xz8q    Created container echoserver
7m59s       Normal    Started                                            pod/hello-minikube-7bc9d7884c-6xz8q    Started container echoserver
8m12s       Normal    SuccessfulCreate                                   replicaset/hello-minikube-7bc9d7884c   Created pod: hello-minikube-7bc9d7884c-6xz8q
8m12s       Normal    ScalingReplicaSet                                  deployment/hello-minikube              Scaled up replica set hello-minikube-7bc9d7884c to 1
24m         Normal    NodeHasSufficientMemory                            node/minikube                          Node minikube status is now: NodeHasSufficientMemory
24m         Normal    NodeHasNoDiskPressure                              node/minikube                          Node minikube status is now: NodeHasNoDiskPressure
24m         Normal    NodeHasSufficientPID                               node/minikube                          Node minikube status is now: NodeHasSufficientPID
24m         Normal    Starting                                           node/minikube                          Starting kubelet.
24m         Normal    NodeHasSufficientMemory                            node/minikube                          Node minikube status is now: NodeHasSufficientMemory
24m         Normal    NodeHasNoDiskPressure                              node/minikube                          Node minikube status is now: NodeHasNoDiskPressure
24m         Normal    NodeHasSufficientPID                               node/minikube                          Node minikube status is now: NodeHasSufficientPID
24m         Normal    NodeAllocatableEnforced                            node/minikube                          Updated Node Allocatable limit across pods
24m         Normal    NodeReady                                          node/minikube                          Node minikube status is now: NodeReady
24m         Normal    RegisteredNode                                     node/minikube                          Node minikube event: Registered Node minikube in Controller
24m         Normal    Starting                                           node/minikube
23m         Normal    Starting                                           node/minikube                          Starting kubelet.
23m         Normal    NodeHasSufficientMemory                            node/minikube                          Node minikube status is now: NodeHasSufficientMemory
23m         Normal    NodeHasNoDiskPressure                              node/minikube                          Node minikube status is now: NodeHasNoDiskPressure
23m         Normal    NodeHasSufficientPID                               node/minikube                          Node minikube status is now: NodeHasSufficientPID
23m         Normal    NodeAllocatableEnforced                            node/minikube                          Updated Node Allocatable limit across pods
7m58s       Warning   listen tcp4 :30067: bind: address already in use   node/minikube                          can't open port "nodePort for default/hello-minikube" (:30067/tcp4), skipping it
```

```
> kubectl get services
NAME             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
hello-minikube   NodePort    10.110.183.166   <none>        8080:30067/TCP   12m
kubernetes       ClusterIP   10.96.0.1        <none>        443/TCP          29m
```

```
> kubectl port-forward service/hello-minikube 7080:8080
Forwarding from 127.0.0.1:7080 -> 8080
Forwarding from [::1]:7080 -> 8080
Handling connection for 7080
Handling connection for 7080
```

```
> curl.exe http://localhost:7080/
CLIENT VALUES:
client_address=127.0.0.1
command=GET
real path=/
query=nil
request_version=1.1
request_uri=http://localhost:8080/

SERVER VALUES:
server_version=nginx: 1.10.0 - lua: 10001

HEADERS RECEIVED:
accept=*/*
host=localhost:7080
user-agent=curl/7.79.1
BODY:
-no body in request-
```

```
> minikube tunnel
â  Tunnel successfully started

ð  æ³¨æ: ãã³ãã«ã«ã¢ã¯ã»ã¹ããã«ã¯ãã®ãã­ã»ã¹ãå­ç¶ããªããã°ãªããªãããããã®ã¿ã¼ããã«ã¯ã¯ã­ã¼ãºããªãã§ãã ãã ...

ð  balanced ãµã¼ãã¹ç¨ã®ãã³ãã«ãèµ·åãã¦ãã¾ãã
```

```
> kubectl get services balanced
NAME       TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
balanced   LoadBalancer   10.97.22.208   127.0.0.1     8080:32332/TCP   39s
```

```
> minikube pause
â¸ï¸  minikube ãã¼ããä¸æåæ­¢ãã¦ãã¾ã ...
â¯ï¸  kube-system, kubernetes-dashboard, storage-gluster, istio-operator ã«å­å¨ãã 18 åã®ã³ã³ããã¼ãä¸æåæ­¢ãã¾ã
ã
```

```
minikube unpause
â¸ï¸  minikube ãã¼ããåç¨¼åããã¦ãã¾ã ...
â¸ï¸  æ¬¡ã®ãã¼ã ã¹ãã¼ã¹ã«å­å¨ãã 18 åã®ã³ã³ããã¼ãåç¨¼åããã¾ãã: kube-system, kubernetes-dashboard, storage-gluster, istio-operator
```

```
> minikube stop
â  ãminikubeããã¼ããåæ­¢ãã¦ãã¾ã...
ð  SSH çµç±ã§ãminikubeãã®é»æºããªãã«ãã¦ãã¾ã...
ð  1 å°ã®ãã¼ããåæ­¢ãã¾ããã
```

```
> minikube config set memory 16384
â  ãããã®å¤æ´ã¯ minikube delete ã®å¾ã« minikube start ãå®è¡ããã¨åæ ããã¾ã
```

```
> minikube addons list
|-----------------------------|----------|--------------|--------------------------------|
|         ADDON NAME          | PROFILE  |    STATUS    |           MAINTAINER           |
|-----------------------------|----------|--------------|--------------------------------|
| ambassador                  | minikube | disabled     | third-party (ambassador)       |
| auto-pause                  | minikube | disabled     | google                         |
| csi-hostpath-driver         | minikube | disabled     | kubernetes                     |
| dashboard                   | minikube | enabled â   | kubernetes                     |
| default-storageclass        | minikube | enabled â   | kubernetes                     |
| efk                         | minikube | disabled     | third-party (elastic)          |
| freshpod                    | minikube | disabled     | google                         |
| gcp-auth                    | minikube | disabled     | google                         |
| gvisor                      | minikube | disabled     | google                         |
| helm-tiller                 | minikube | disabled     | third-party (helm)             |
| ingress                     | minikube | disabled     | unknown (third-party)          |
| ingress-dns                 | minikube | disabled     | google                         |
| istio                       | minikube | disabled     | third-party (istio)            |
| istio-provisioner           | minikube | disabled     | third-party (istio)            |
| kong                        | minikube | disabled     | third-party (Kong HQ)          |
| kubevirt                    | minikube | disabled     | third-party (kubevirt)         |
| logviewer                   | minikube | disabled     | unknown (third-party)          |
| metallb                     | minikube | disabled     | third-party (metallb)          |
| metrics-server              | minikube | disabled     | kubernetes                     |
| nvidia-driver-installer     | minikube | disabled     | google                         |
| nvidia-gpu-device-plugin    | minikube | disabled     | third-party (nvidia)           |
| olm                         | minikube | disabled     | third-party (operator          |
|                             |          |              | framework)                     |
| pod-security-policy         | minikube | disabled     | unknown (third-party)          |
| portainer                   | minikube | disabled     | portainer.io                   |
| registry                    | minikube | disabled     | google                         |
| registry-aliases            | minikube | disabled     | unknown (third-party)          |
| registry-creds              | minikube | disabled     | third-party (upmc enterprises) |
| storage-provisioner         | minikube | enabled â   | google                         |
| storage-provisioner-gluster | minikube | disabled     | unknown (third-party)          |
| volumesnapshots             | minikube | disabled     | kubernetes                     |
|-----------------------------|----------|--------------|--------------------------------|
```

```
> minikube start -p aged --kubernetes-version=v1.16.1
ð  Microsoft Windows 10 Home 10.0.19044 Build 19044 ä¸ã® [aged] minikube v1.25.2
â¨  docker ãã©ã¤ãã¼ãèªåçã«é¸æããã¾ãããä»ã®é¸æè¢: virtualbox, ssh

â  MK_USAGE ãåå ã§çµäºãã¾ã: Docker Desktop ã¯ 5942MB ã®ã¡ã¢ãªã¼ããä½¿ç¨ã§ãã¾ãããã16384MB ã®ã¡ã¢ãªã¼ä½¿ç¨ãæå®ããã¾ãã
```

```
minikube config set memory 5942
â  ãããã®å¤æ´ã¯ minikube delete ã®å¾ã« minikube start ãå®è¡ããã¨åæ ããã¾ã
```

```
> minikube start -p aged --kubernetes-version=v1.16.1
ð  Microsoft Windows 10 Home 10.0.19044 Build 19044 ä¸ã® [aged] minikube v1.25.2
â¨  docker ãã©ã¤ãã¼ãèªåçã«é¸æããã¾ãããä»ã®é¸æè¢: virtualbox, ssh
ð  aged ã¯ã©ã¹ã¿ã¼ä¸­ã®ã³ã³ãã­ã¼ã«ãã¬ã¼ã³ã® aged ãã¼ããèµ·åãã¦ãã¾ã
ð  ãã¼ã¹ã¤ã¡ã¼ã¸ãåå¾ãã¦ãã¾ã...
ð¥  docker container (CPUs=2, Memory=5942MB) ãä½æãã¦ãã¾ã...
ð³  Docker 20.10.12 ã§ Kubernetes v1.16.1 ãæºåãã¦ãã¾ã...
    âª kubelet.housekeeping-interval=5m
    > kubectl.sha1: 41 B / 41 B [----------------------------] 100.00% ? p/s 0s
    > kubelet.sha1: 41 B / 41 B [----------------------------] 100.00% ? p/s 0s
    > kubeadm.sha1: 41 B / 41 B [----------------------------] 100.00% ? p/s 0s
    > kubeadm: 42.20 MiB / 42.20 MiB [-------------] 100.00% 16.50 MiB p/s 2.8s
    > kubelet: 117.43 MiB / 117.43 MiB [-----------] 100.00% 23.52 MiB p/s 5.2s
    > kubectl: 44.52 MiB / 44.52 MiB [--------------] 100.00% 8.24 MiB p/s 5.6s
    âª è¨¼ææ¸ã¨éµãä½æãã¦ãã¾ã...
    âª ã³ã³ãã­ã¼ã«ãã¬ã¼ã³ãèµ·åãã¦ãã¾ã...
    âª RBAC ã®ã«ã¼ã«ãè¨­å®ä¸­ã§ã...
ð  Kubernetes ã³ã³ãã¼ãã³ããæ¤è¨¼ãã¦ãã¾ã...
    âª gcr.io/k8s-minikube/storage-provisioner:v5 ã¤ã¡ã¼ã¸ãä½¿ç¨ãã¦ãã¾ã
ð  æå¹ãªã¢ããªã³: storage-provisioner, default-storageclass

â  C:\Program Files\Docker\Docker\resources\bin\kubectl.exe ã®ãã¼ã¸ã§ã³ã¯ 1.21.3 ã§ãKubernetes 1.16.1 ã¨äºææ§ã
ãªãããããã¾ããã
    âª kubectl v1.16.1 ãå¿è¦ã§ããï¼ 'minikube kubectl -- get pods -A' ãè©¦ãã¦ã¿ã¦ãã ãã
ð  å®äºãã¾ããï¼ kubectl ãã"aged"ãã¯ã©ã¹ã¿ã¨ã"default"ããã¼ã ã¹ãã¼ã¹ãä½¿ç¨ããããæ§æããã¾ãã
```

```
> minikube delete --all
ð¥  docker ã®ãagedããåé¤ãã¦ãã¾ã...
ð¥  C:\Users\yuto2\.minikube\machines\aged ãåé¤ãã¦ãã¾ã...
ð  ã¯ã©ã¹ã¿ã¼ãagedãã®å¨ã¦ã®ãã¬ã¼ã¹ãåé¤ãã¾ããã
ð¥  docker ã®ãminikubeããåé¤ãã¦ãã¾ã...
ð¥  C:\Users\yuto2\.minikube\machines\minikube ãåé¤ãã¦ãã¾ã...
ð  ã¯ã©ã¹ã¿ã¼ãminikubeãã®å¨ã¦ã®ãã¬ã¼ã¹ãåé¤ãã¾ããã
ð¥  å¨ã¦ã®ãã­ãã¡ã¤ã«ã®åé¤ã«æåãã¾ãã
```
