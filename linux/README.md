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


