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


## COntinue with the installation once the cluster shows up

<img width="2920" alt="image" src="https://github.com/user-attachments/assets/62d499e4-6c6a-4956-9187-635b86861e28" />


