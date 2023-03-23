---

### docker sudo fix:

sudo groupadd docker  
sudo usermod -aG docker ${USER}  
su -s ${USER}  OR logout/login  
docker run hello-world  

if it doesn't work AFTER a modification (update, upgrade etc.)  
sudo chmod 666 /var/run/docker.sock

---

### write into a container volume/file using exec:  

docker exec container_name sh/bash -c "echo 'some text' >> volume/file_name"  

---  

### fix docker autocomplete not workig:  

add the below to .zshrc:  

autoload -Uz compinit  
compinit  

---  

### fix git repo caching in Dockerfile:  

"If you use GitHub (or gitlab or bitbucket too most likely) you can ADD the GitHub API's representation of your repo to a dummy location."  

ADD https://api.github.com/repos/$USER/$REPO/git/refs/heads/$BRANCH version.json  
RUN git clone -b $BRANCH https://github.com/$USER/$REPO.git $GIT_HOME/  

The API call will return different results when the head changes, invalidating the docker cache.  
//  
"If you're dealing with private repos you can use github's x-oauth-basic authentication scheme with a personal access token like so:"  

ADD https://$ACCESS_TOKEN:x-oauth-basic@api.github.com/repos/$USER/$REPO/git/refs/heads/$BRANCH version.json

---  

### reduce the size of a log file for running docker container:  

docker inspect --format='{{.LogPath}}' container_name  

yum install util-linux  

sudo fallocate --collapse-range --offset 0 --length 10GiB /path/to/logfile-json.log  
The above command deallocates the space from position 0 to the next 10GBs (adjust length to match)  
for example  if the log file size is 15GB it will remove the first/oldest 10GBs  

To setup log rotation:  

echo '{"log-driver": "json-file", "log-opts": {"max-size": "10m", "max-file": "3"}}' | jq . > /etc/docker/daemon.json \
  && systemctl restart docker  
  

---  


