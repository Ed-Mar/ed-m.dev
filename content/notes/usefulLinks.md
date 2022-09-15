---
title: Useful Links
date: 2022-08-27T8:58:18-04:00
tags: kubernetes

---
### 220827
- [minikube addon ingress-dns](https://minikube.sigs.k8s.io/docs/tutorials/custom_cert_ingress/)
- [MKCERT: VALID HTTPS CERTIFICATES FOR LOCALHOST](https://words.filippo.io/mkcert-valid-https-certificates-for-localhost/)
- [Using mkcert to quickly create certificates for testing and development environments](https://prefetch.net/blog/2020/06/29/using-mkcert-to-quickly-create-certificates-for-testing-and-development-environments/)
- [cert-manager Config CA](https://cert-manager.io/docs/configuration/ca/)
- [Setting up local Cert-Manager](https://someweb.github.io/devops/cert-manager-kubernetes/)
- [Oliver Coding Installing Keycloak](https://www.olivercoding.com/2021-01-16-kubernetes-keycloak/)

```bash
helm install  \
 cert-manager jetstack/cert-manager \
 --namespace cert-manager \
 --create-namespace \
 --version v1.9.1 \
 --set installCRDs=true
```