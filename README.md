# Appswitch
k8s  istio net  docker

[appswitch](https://appswitch.readthedocs.io/en/latest/overview.html)
[appswitch-blog](http://appswitch.io/blog/kubernetes_istio_and_network_function_devirtualization_with_appswitch/)

## Deploy appswitch to kubernetes cluster with daemonset

```bash
  kubectl apply -f appswitch.yaml
  ax get nodes
  kubectl apply -f nginx-demo.yaml 
```
## Visit nginx demo service

```bash
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


