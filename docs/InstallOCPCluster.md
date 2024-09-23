### Install an OCP cluster using Assisted Installer
1. For ODF + CNV the requirements: 
   1. 3 VMs each at least:
      1. 40GB RAM
      2. 20 CPU
      3. 2 hosts disks: 50GB (for openshift installation) and 100 GB (for ODF)
      
   2. The command: 
   ```sudo virt-install --name host3 --memory 41984 --vcpus 20 --disk size=50 --disk size=100 --os-variant rhel9.0 --cdrom discovery_image_assisted-migration.iso```
   
2. Install MTV - [ROY]
   1. create forklift controller for some reason it wasn't create the first time
   2. If there is any issue - check in the workloads pods
   3. Create new provider 
      1. vddk
      2. username + password
3. Storage class - Set a default for virtualization using the annotation:[ROY] 
   ```storageclass.kubevirt.io/is-default-virt-class```
4. create an appropriate NAD  [ROY]