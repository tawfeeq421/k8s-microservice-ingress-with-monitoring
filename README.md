kubectl create secret tls amazon-tls \
  --cert=cert.crt \
  --key=key.key \
  -n prod
