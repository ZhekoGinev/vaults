### Get historical data on a repo (bash)  

git for-each-ref --sort='-committerdate:iso8601' --format='%(committerdate:relative)|%(refname:short)|%(committername)' refs/remotes/ | column -s '|' -t > ./git-report-$(date +"%d-%m-%y").txt  

---  

### Create, delete, manage tags  

Create - https://devconnected.com/how-to-create-git-tags/  
Delete - https://devconnected.com/how-to-delete-local-and-remote-tags-on-git/  

---  

### Branching Strategies:  
- git flow ([nvie.com](https://nvie.com/posts/a-successful-git-branching-model)   |   [Atlassian.com](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow))
- trunk-based ([Atlassian.com](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development))
