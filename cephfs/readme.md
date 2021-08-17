```bash
ceph osd pool create cephfs_data 16
ceph osd pool create cephfs_metadata 16
ceph fs new cephfs cephfs_metadata cephfs_data

ceph auth get-or-create client.fs mon 'allow r' mgr 'allow rw' mds 'allow rw' osd 'allow rw pool=cephfs_data, allow rw pool=cephfs_metadata'
# Copy key to secret
```
