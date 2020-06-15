# np-troubleshoot

```bash
> k apply -f np-broken.yaml
networkpolicy.networking.k8s.io/quickstart-tcp-proxy created
networkpolicy.networking.k8s.io/quickstart-http-proxy created
networkpolicy.networking.k8s.io/quickstart-engine created
networkpolicy.networking.k8s.io/quickstart-asperanoded created
networkpolicy.networking.k8s.io/quickstart-asperanoded-master created
networkpolicy.networking.k8s.io/quickstart-prometheus created
networkpolicy.networking.k8s.io/quickstart-http-scheduler created
networkpolicy.networking.k8s.io/quickstart-tcp-scheduler created
networkpolicy.networking.k8s.io/quickstart-ascp created
networkpolicy.networking.k8s.io/quickstart-default-deny-all created
> curl -m 5 -ki https://quickstart-http-proxy-hsts.apps.aspera-us-west-2.icp4i.com/ping
curl: (28) Operation timed out after 5000 milliseconds with 0 bytes received
> k delete networkpolicy --all
networkpolicy.networking.k8s.io "quickstart-ascp" deleted
networkpolicy.networking.k8s.io "quickstart-asperanoded" deleted
networkpolicy.networking.k8s.io "quickstart-asperanoded-master" deleted
networkpolicy.networking.k8s.io "quickstart-default-deny-all" deleted
networkpolicy.networking.k8s.io "quickstart-engine" deleted
networkpolicy.networking.k8s.io "quickstart-http-proxy" deleted
networkpolicy.networking.k8s.io "quickstart-http-scheduler" deleted
networkpolicy.networking.k8s.io "quickstart-prometheus" deleted
networkpolicy.networking.k8s.io "quickstart-tcp-proxy" deleted
networkpolicy.networking.k8s.io "quickstart-tcp-scheduler" deleted
> k apply -f np.yaml
networkpolicy.networking.k8s.io/quickstart-tcp-proxy created
networkpolicy.networking.k8s.io/quickstart-engine created
networkpolicy.networking.k8s.io/quickstart-asperanoded created
networkpolicy.networking.k8s.io/quickstart-asperanoded-master created
networkpolicy.networking.k8s.io/quickstart-prometheus created
networkpolicy.networking.k8s.io/quickstart-http-scheduler created
networkpolicy.networking.k8s.io/quickstart-tcp-scheduler created
networkpolicy.networking.k8s.io/quickstart-ascp created
networkpolicy.networking.k8s.io/quickstart-http-proxy created
networkpolicy.networking.k8s.io/quickstart-default-deny-all created
> curl -m 5 -ki https://quickstart-http-proxy-hsts.apps.aspera-us-west-2.icp4i.com/ping
HTTP/1.1 200
content-length: 0
date: Mon, 15 Jun 2020 19:47:01 GMT
set-cookie: f591ba3ad440f0e8f9326145b293cb18=5879ca70db802b2972b2300afe3d566a; path=/; HttpOnly; Secure
cache-control: private
```