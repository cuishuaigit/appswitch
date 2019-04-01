# Appswitch
k8s  istio net  docker

[appswitch](https://appswitch.readthedocs.io/en/latest/overview.html)
[appswitch-blog](http://appswitch.io/blog/kubernetes_istio_and_network_function_devirtualization_with_appswitch/)
[my-blog](https://www.cnblogs.com/cuishuai/p/10622617.html)
## Deploy appswitch to kubernetes cluster with daemonset

```bash
  kubectl apply -f appswitch.yaml
  
  ax get nodes
  
  NAME   CLUSTER        IP       EXTERNALIP    ROLE     APPCOUNT
-----------------------------------------------------------------
  k3-3  cluster0  10.42.8.28              [compute]  1
  k3-2  cluster0  10.42.7.10              [compute]  1
  k3-1  cluster0  10.42.6.7               [compute]  2
 
  kubectl apply -f nginx-demo.yaml 
```
## Visit nginx demo service

```bash
  ax get vservices

      VSNAME    VSTYPE   VSIP     VSPORTS   VSBACKENDIPS                 VSAPPIDS
----------------------------------------------------------------------------------------------
  nginx-demo  Random  1.1.1.1  [{80 80}]  []            [30d2f4f1-6184-4d05-bcbc-6c585c9f0227]


  ax run -- curl -I nginx-demo

  HTTP/1.1 200 OK
  Server: nginx/1.15.10
  Date: Mon, 01 Apr 2019 09:25:50 GMT
  Content-Type: text/html
  Content-Length: 612
  Last-Modified: Tue, 26 Mar 2019 14:04:38 GMT
  Connection: keep-alive
  ETag: "5c9a3176-264"
  Accept-Ranges: bytes
```

## Reference 
 
  https://appswitch.readthedocs.io/en/latest/overview.html
  http://appswitch.io/blog/kubernetes_istio_and_network_function_devirtualization_with_appswitch/
  https://www.cnblogs.com/cuishuai/p/10622617.html
