<details>
  <summary>Basic Cheat Sheet</summary>
  <img src="https://github.com/ZhekoGinev/DevOps/blob/main/Linux/images/a%20very%20good%20basic%20cheat%20sheet.png"></img>
</details>

---

### balena entcher gpu fix  
--disable-gpu-sandbox  
(also pacman -S fuse2 on Arch)  

---

### Resolution fix for VirtualBox  
(provide full path to VBoxManage.exe on Windows or open PS within the folder) and then run  

VBoxManage.exe setextradata "VM_Name" "GUI/LastGuestSizeHint" "1920,1080"

---

### Install latest version of git on Centos 7  
sudo yum -y remove git  
sudo yum -y remove git-*  
sudo yum -y install https://packages.endpointdev.com/rhel/7/os/x86_64/endpoint-repo.x86_64.rpm  
sudo yum -y install git  

---

### Resolution fix for Hyper-V:  

set-vmvideo VM_NAME -horizontalresolution:1600 -verticalresolution:900 -resolutiontype single  

---  

### Run command as another user:  

runuser -l userNameHere -c 'command'  

---  

### Swap file mgmt  

check swap - swapon -s  

check if swap is configured to run at start - cat /etc/fstab  

check swappiness - sudo cat /proc/sys/vm/swappiness  (There should be ann entry like "/swapfile   swap    swap    defaults        0 0")  

cycle swap by turning it off - sudo swapoff <swap_name> or -a for all, then when the memory is recovered - sudo swapon <swap_name>/-a  

want to change swap size?  

sudo swapoff -a
sudo fallocate -l <size>(e.g. 2G) /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile  
  
---  

