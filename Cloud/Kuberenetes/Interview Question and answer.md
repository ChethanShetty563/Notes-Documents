### 1.  What is Kubernetes and what problem does it solve?
		* Kuberenetes is an open source platform for automating the deployment, scaling and       management of containerized application
		* It provides a way to orchestrate containers, which are lightweight and portable units of software that can run on any infrstructure.
		* Kuberenetes solves the managment of containerized applications in a production environment
		* It handles the tasks such as scaling, self healing, networking and service discovery, making it easier to deploy update and maintain complex applications.
		* It provides a consistent and predictable environment for deploying and managing containerized applications across different environments such as on-premise and in cloud.

### 2.  How does Kubernetes handle container orchestration?
		* Kuberenetes handles the conatiner orchestration by using the set of abstraction that represents the deisred state of system, and  control loop that keeps on compares the current state of sytem to the desired state and makes the necessary change to bring to the desired state.
		* The main abstractions are :
			* Pods : A pod is a smallest and simple unit i uberenetes object model that represents a running process on a cluster. It may conatin one or more containers and these are the building block of kuberenetes 
			* Replication Controllers: Replication Controllers are used to ensure that a specified number of replicas of a pod are running at any given time. If any pod goes down, the Replication controller automatically starts a new one to replace it.
			* Services : Services provides a stable endpoints for pods and allow pods to be accessed by other pods or by external clients.
			* Deployments: Deployments are used to declaratively manage the desired state of a set of replica sets and pods. They provide a way to perform rolling updates and rollbacks.
			* StatefulSets : Statefulsets are used to manage stateful applications that require stable storage and network identities.

### 3.  Can you explain the main components of a Kubernetes cluster?
		The main components of Kuberenetes are :
		1. Master Nodes : These are the nodes that manage the overall state of the cluster and are responsible for scheduling and scaling the worker nodes. The master nodes run the kuberenetes control plane which includes components such as the API server , etcd and the controller manger.
		2. Worker nodes : These are the nodes that run the containerized applications and are managed by the master nodes.The worker nodes run the kubelet, which is an agent that communicates with the master nodes to receive instructions and report the status of the containers running on the node.
		3. etcd: This is distributed key value store that stores the configuration data of the cluster, such as the current state and the desired state and details of the individual nodes.
		4. API Server : This is the main entry point for all communication with the Kubernetes cluster. It exposes a RESTful API that can be used to create, read, update, and delete resources in the cluster.
		5. Controller manager : This component is responsible for monitoring the state of the cluster and making adjustments as necessary to bring the system to the desired state. It works in conjunction with the etcd and the API server.
		6. Kubelet : The kubelet is an agent that runs on each worker node and is responsible for communicating with the master nodes. It receives instructions from the master nodes and ensures that the desired state of the system is reflected on the worker node.
		7. Kube-proxy : This is a network proxy that runs on each worker node and is responsible for routing network traffic to the correct pods.
		8. Kubernetes CNI(Conatiner Network Interface) : Kubernetes CNI is a set of networking plugins that provide an abstraction for the networking layer in Kubernetes. It is responsible for allocating IP addresses to Pods and Services and for providing network connectivity between Pods.


2.  How does Kubernetes handle scaling and self-healing of applications?
3.  Can you explain the difference between a Kubernetes Pod and a Deployment?
4.  How does Kubernetes handle networking and service discovery?
5.  How does Kubernetes handle security and access control?
6.  Can you explain the use of Kubernetes ConfigMaps and Secrets?
7.  How can you monitor and troubleshoot a Kubernetes cluster?
8.  How does Kubernetes integrate with other tools and platforms, such as CI/CD pipelines or cloud providers?