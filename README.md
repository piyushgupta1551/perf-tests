# Kubernetes perf-tests

[![Go Report Card](https://goreportcard.com/badge/github.com/kubernetes/perf-tests)](https://goreportcard.com/report/github.com/kubernetes/perf-tests)

This repo is dedicated for storing various Kubernetes-related performance test related tools. If you want to add your own load-test, benchmark, framework or other tool please contact with one of the Owners.

Because in general tools are independent and have their own ways of being configured or run, each subdirectory needs a separate README.md file with the description of its contents.

## Repository setup

To run all verify* scripts before pushing to remote branch (useful for catching problems quickly) execute:

```
cp _hook/pre-push .git/hooks/pre-push
```

## NOTE for running perf-tests in ppc64le single node cluster

If you have created a single node containerd kubernetes cluster using https://github.com/ppc64le-cloud/k8s-ansible, add the below entries to your /root/.bashrc file on the edge/bastion/cluster node so that these env variables are initialsed in every session - 
```
export ETCD_HOST=<host IP>
export ETCD_CERTIFICATE=/etc/kubernetes/pki/etcd/peer.crt
export ETCD_KEY=/etc/kubernetes/pki/etcd/peer.key
export GOPATH=/usr/bin/go/bin OR export GOPATH=<path for perf-scale repo clone>
export NODE_PRELOAD_IMAGES=gcr.io/google_containers/pause:3.1
```
