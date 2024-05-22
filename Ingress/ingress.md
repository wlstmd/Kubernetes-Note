## Ingress 만들기

```bash
# minikube에 Ingress 활성화하기
minikube addons enable ingress

# ingress 컨트롤러 확인
kubectl -n ingress-nginx get pod
```

실행결과

```bash
NAME                                        READY   STATUS      RESTARTS   AGE
ingress-nginx-admission-create-n2684        0/1     Completed   0          96s
ingress-nginx-admission-patch-thq42         0/1     Completed   1          96s
ingress-nginx-controller-6d5f55986b-jkcfs   1/1     Running     0          96s
```

```bash
minikube service ingress-nginx-controller -n ingress-nginx --url
```

실행결과

```bash
🏃  Starting tunnel for service ingress-nginx-controller.
|---------------|--------------------------|-------------|------------------------|
|   NAMESPACE   |           NAME           | TARGET PORT |          URL           |
|---------------|--------------------------|-------------|------------------------|
| ingress-nginx | ingress-nginx-controller |             | http://127.0.0.1:51728 |
|               |                          |             | http://127.0.0.1:51729 |
|---------------|--------------------------|-------------|------------------------|
http://127.0.0.1:51728
http://127.0.0.1:51729
```

#### curl -I http://192.168.49.2/healthz # minikube ip를 입력

실행결과

```bash
HTTP/1.1 200 OK
Date: Sat, 05 Dec 2020 13:53:37 GMT
Content-Type: text/html
Content-Length: 0
Connection: keep-alive
```
