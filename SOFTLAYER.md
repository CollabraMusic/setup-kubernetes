#Install Stuff

`
ansible-playbook -i inventory/inventory.cfg cluster.yml -u root
git submodule init roles/apps/k8s-common roles/apps/k8s-kubedns roles/apps/k8s-kube-ui
git submodule update
ansible-playbook -i inventory/inventory.cfg apps.yml -u root
`

#Kube Config
You should put these somewhere that you can refer to them from your ~/.kube/config file

`
scp root@k8-master.collabra.softlayer.com:/etc/kubernetes/ssl/admin-key.pem ./admin-key.pem
scp root@k8-master.collabra.softlayer.com:/etc/kubernetes/ssl/admin.pem ./admin.pem
scp root@k8-master.collabra.softlayer.com:/etc/kubernetes/ssl/ca.pem ./ca.pem
`

