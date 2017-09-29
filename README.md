# helm-repo-in-github

This is a sample for how to setup a helm repo in github without gh-pages. This is usable even for private repositories.


# Adding a new version or chart to this repo

```bash
$ helm package $YOUR_CHART_PATH/ # build the tgz file and copy it here
$ helm repo index . # create or update the index.yaml for repo
$ git add .
$ git commit -m 'New chart version'
```

# How to use it as a helm repo

You might know github has a raw view. So simply use the following:

```bash
$ helm repo add sample 'https://raw.githubusercontent.com/kmzfs/helm-repo-in-github/master/'
$ helm repo update
$ helm search aerospike
NAME            	VERSION	DESCRIPTION
sample/aerospike	0.1.2  	A Helm chart for Aerospike in Kubernetes
```

If your repo is private you can create a "Personal access tokens" and use it like:

```bash
$ helm repo add sample 'https://MY_PRIVATE_TOKEN@raw.githubusercontent.com/kmzfs/helm-repo-in-github/master/'
```

Note: Becareful who is creating the token and what is its level of access.