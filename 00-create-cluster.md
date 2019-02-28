## Create a cluster

Most of the Kubernetes installation methods out there do not get you a cluster
with [Network
Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
feature. You manually need to install and configure a Network Policy provider
such as Weave Net or Calico.


大多数`Kubernete`安装方法都没有为您提供集群的`Network Policies(也就是网络策略)`功能。您需要手动安装和配置网络策略提供程序
例如`Weave Net`或`Calico`。这里我们推荐使用`calico`

**[Google Kubernetes Engine (GKE)][gke]** easily lets you get a Kubernetes
cluster with Network Policies feature. You do not need to install a network
policy provider yourself, as GKE configures Calico as the networking provider
for you. (This feature is generally available as of GKE v1.10.)

`GKE`轻松让你得到一个具有网络策略功能的`Kubernetes`群集，您不需要自己来安装网络
策略，因为GKE将为了你配置`Calico`为网络提供商。 （此功能通常从GKE v1.10开始提供。）

To create a GKE cluster named `np` with Network Policy feature enabled, run:

    gcloud beta container clusters create np \
        --enable-network-policy \
        --zone us-central1-b

This will create a 3-node Kubernetes cluster on Kubernetes Engine and turn on
the Network Policy feature.

现在将会有一个三节点的`Kubernetes`集群在`Kubernetes`引擎里，并且这个集群已经开启了网络策略。

Once you complete this tutorial, you can delete the cluster by running:

    gcloud container clusters delete -q --zone us-central1-b np


[gke]: https://cloud.google.com/kubernetes-engine/
