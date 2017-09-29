# helm-repo-in-github

This is a sample for how to setup a helm repo in github without gh-pages. This is usable even for private repositories.


# Adding a new version or chart to this repo

```bash
$ 
$ helm package $YOUR_CHART_PATH/ # build the tgz file and copy it here
$ helm repo index . # create or update the index.yaml for repo
$ git add .
$ git commit -m 'New chart version'
```

# How to use it as a helm repo

If you have missed github as a raw review. So simply use the following

helm repo add sample 'https://raw.githubusercontent.com/kmzos/helm-repo-in-github/master'