```bash
ceph osd pool create kube 16
ceph osd pool application enable kube kubernetes
ceph auth get-or-create client.rbdkube mon 'allow r, allow command "osd blacklist"' osd 'allow rwx pool=kube'
# Copy key to secret
```
