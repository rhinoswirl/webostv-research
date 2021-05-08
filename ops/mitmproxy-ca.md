# Injecting mitmproxy CA

Note: see [Filesystem overlays](fs-overlays.md), /usr/share/ca-certificates/sdp + /etc/ssl/certs

```
mkdir -p /tmp/overlayfs/upper /tmp/overlayfs/work && mount -t overlay -o lowerdir=/etc/ssl/,upperdir=/tmp/overlayfs/upper/,workdir=/tmp/overlayfs/work/ overlay-ssl /etc/ssl/
cd /etc/ssl/certs
curl http://mitm.it/cert/pem > mitmproxy.crt
ln -s mitmproxy.crt $(openssl x509 -in /etc/ssl/certs/mitmproxy.crt -subject_hash_old -noout).0
cat mitmproxy.crt >> trusted_cas.crt
cat mitmproxy.crt >> ca-certificates.crt

# Also TODO: /usr/share/ca-certificates/sdp
```