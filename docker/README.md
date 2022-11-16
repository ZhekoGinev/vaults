---

### docker sudo fix:

sudo groupadd docker  
sudo usermod -aG docker ${USER}  
su -s ${USER}  OR logout/login  
docker run hello-world  

if it doesn't work AFTER a modification (update, upgrade etc.)  
sudo chmod 666 /var/run/docker.sock

---
