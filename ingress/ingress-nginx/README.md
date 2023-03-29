
### Ingress Controller
```bash
# [ VERSION INPUT ]은 https://github.com/kubernetes/ingress-nginx/releases에서 버전을 찾는다.
# kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/[ VERSION INPUT ]/deploy/static/provider/cloud/deploy.yaml
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.6.4/deploy/static/provider/cloud/deploy.yaml

# 배포된 ingress controller의 상태를 확인한다.
$ kubectl -n ingress-nginx get all
```

### 샘플 manifest file을 배포하여 테스트 해본다.
```bash
$ kubectl apply -f .

or

$ kubectl apply -f deployment.yml
$ kubectl apply -f service.yml
$ kubectl apply -f ingress.yml


# demo.localdev.me 접속 시 `It works!` 출력된 페이지로 연결된다.
```



```bash
$ openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls.key -out tls.crt -subj "/CN=demo.com"

$ kubectl create secret tls demo-secret --cert tls.crt --key tls.key 
```
