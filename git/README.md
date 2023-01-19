### Get historical data on a repo (bash)  

git for-each-ref --sort='-committerdate:iso8601' --format='%(committerdate:relative)|%(refname:short)|%(committername)' refs/remotes/ | column -s '|' -t > ./git-report-$(date +"%d-%m-%y").txt  

---  

