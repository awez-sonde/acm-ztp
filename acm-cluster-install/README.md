# Creating a SNO cluster using assited service 

## Go to https://console.redhat.com/openshift/create/datacenter

<img width="2979" alt="image" src="https://github.com/user-attachments/assets/c63f35d4-a4ed-4995-8b57-c592e6eb58c5" />


## Use interactive web based 

<img width="2996" alt="image" src="https://github.com/user-attachments/assets/6ec39b0b-99bb-45a0-95ea-171fa46d5470" />

## Filling the initial details

<img width="2962" alt="image" src="https://github.com/user-attachments/assets/74d46d40-48a2-4a2a-970b-9ec8097c5482" />


## Using LVM storage and Multicluster engine operator


<img width="1878" alt="image" src="https://github.com/user-attachments/assets/89a0c282-ca8e-4e4c-af91-cdee6f4ad009" />


## Add host and add ssh key to download minimal iso

<img width="2567" alt="image" src="https://github.com/user-attachments/assets/c1f8ec83-0bdb-4db3-977d-9faae6ac973c" />


## Downloading the ISO to be used by ACM cluster

```
[root@kvm ~]# wget -O discovery_image_acm-ztp.iso 'https://api.openshift.com/api/assisted-images/bytoken/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3NTEzOTQwODMsInN1YiI6ImZlYmUyOGEyLTAyZDAtNGFiNy04ZjZkLTIxZjVmODYxYWEyYyJ9.sf5BE1jkR-SZjc3_RQFWLs7Ij5otWzeaVfnV5e4VytA/4.16/x86_64/minimal.iso'
--2025-07-01 10:21:54--  https://api.openshift.com/api/assisted-images/bytoken/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3NTEzOTQwODMsInN1YiI6ImZlYmUyOGEyLTAyZDAtNGFiNy04ZjZkLTIxZjVmODYxYWEyYyJ9.sf5BE1jkR-SZjc3_RQFWLs7Ij5otWzeaVfnV5e4VytA/4.16/x86_64/minimal.iso
Resolving api.openshift.com (api.openshift.com)... 52.2.73.229, 44.218.36.79, 34.200.195.94
Connecting to api.openshift.com (api.openshift.com)|52.2.73.229|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 113317888 (108M) [application/octet-stream]
Saving to: 'discovery_image_acm-ztp.iso'

discovery_image_acm-ztp.iso                100%[========================================================================================>] 108.07M  15.5MB/s    in 8.1s    

2025-07-01 10:22:03 (13.3 MB/s) - 'discovery_image_acm-ztp.iso' saved [113317888/113317888]

[root@kvm ~]# mv discovery_image_acm-ztp.iso /var/lib/libvirt/images/
```


## Create a machine uing the image as a boot source

<img width="1556" alt="image" src="https://github.com/user-attachments/assets/b508e92a-b971-4478-a1e1-82d35cb4eca0" />


## Continue with the installation once the cluster shows up

<img width="2920" alt="image" src="https://github.com/user-attachments/assets/62d499e4-6c6a-4956-9187-635b86861e28" />

<img width="1652" alt="image" src="https://github.com/user-attachments/assets/c4ccc788-f854-4730-9743-0aaa00f8eeee" />

## Verify the installation

```
[root@kvm acm-ztp]# oc get co
NAME                                       VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE   MESSAGE                                                  
authentication                             4.16.42   True        False         False      42m                                                              
baremetal                                  4.16.42   True        False         False      64m                                                              
cloud-controller-manager                   4.16.42   True        False         False      59m                                                              
cloud-credential                           4.16.42   True        False         False      66m                                                              
cluster-autoscaler                         4.16.42   True        False         False      63m                                                              
config-operator                            4.16.42   True        False         False      66m                                                              
console                                    4.16.42   True        False         False      42m                                                              
control-plane-machine-set                  4.16.42   True        False         False      63m                                                              
csi-snapshot-controller                    4.16.42   True        False         False      66m                                                              
dns                                        4.16.42   True        False         False      56m                                                              
etcd                                       4.16.42   True        False         False      57m                                                              
image-registry                             4.16.42   True        False         False      56m                                                              
ingress                                    4.16.42   True        False         False      66m                                                              
insights                                   4.16.42   True        False         False      62m                                                              
kube-apiserver                             4.16.42   True        False         False      55m                                                              
kube-controller-manager                    4.16.42   True        False         False      57m                                                              
kube-scheduler                             4.16.42   True        False         False      55m                                                              
kube-storage-version-migrator              4.16.42   True        False         False      66m                                                              
machine-api                                4.16.42   True        False         False      62m                                                              
machine-approver                           4.16.42   True        False         False      65m                                                              
machine-config                             4.16.42   True        False         False      63m                                                              
marketplace                                4.16.42   True        False         False      63m                                                              
monitoring                                 4.16.42   True        False         False      50m                                                              
network                                    4.16.42   True        False         False      66m                                                              
node-tuning                                4.16.42   True        False         False      66m                                                              
openshift-apiserver                        4.16.42   True        False         False      55m                                                              
openshift-controller-manager               4.16.42   True        False         False      58m                                                              
openshift-samples                          4.16.42   True        False         False      55m                                                              
operator-lifecycle-manager                 4.16.42   True        False         False      64m                                                              
operator-lifecycle-manager-catalog         4.16.42   True        False         False      64m                                                              
operator-lifecycle-manager-packageserver   4.16.42   True        False         False      56m                                                              
service-ca                                 4.16.42   True        False         False      66m                                                              
storage                                    4.16.42   True        False         False      66m                                                              
[root@kvm acm-ztp]#

```



