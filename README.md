# jun25-kubernetes-practice
Practicing Kubernetes using minikube

## Core Kubernetes Concepts

### Cluster
 - A cluster is the full Kubernetes environment
 - eg. School System (cluster) managing students (apps)

### Node
- A machine that runs your workloads
- eg. A classroom or a building (node) where the students learn (apps run)

### Pod
- The basic deployable unit in Kubernetes
- eg. A student/desk (pod) in a classroom (node)

### Deployment
- A deployment manages the pods declaratively
- eg. A teacher (deployment) keeps the right number of students (pod) in class (node)

### Service
- A service gives a stable network access to the pods
- eg. The front desk/reception (service) where visitors/students ask for directions to buildings/classrooms (pods)

### Notable mentions
- ClusterIP: internal-only, is provided by default
- NortPort: exposes the app on a port of the node, is best for local work
- LoadBalancer: Distribute request loads across different pods
- ControlPlane: Keeps it all working

# Getting Start
Creates and starts a local kubernetes cluster with Docker as the runtime environment
```minikube start --driver=docker```

Shows where the K8s control plane is running
```kubectl cluster-info```

List of nodes that exist in the cluster
```kubectl get nodes```

Create a deployment named demo-minikube using the image: https://hub.docker.com/r/kicbase/echo-server/tags
```kubectl create deployment demo-minikube --image=kicbase/echo-server:1.0```

Shows a list of all the deployments
```kubectl get deployment```

Show a list of all the pods
```kubectl get pods```

Shows the description of the demo-minikube deployment
```kubectl describe deployment demo-minikube```

Make multiple pods of the same image inside the deployment
```kubectl scale deployment demo-minikube --replicas=3```

Expose the demo-minikube deployment through port 8080 
```kubectl expose deployment demo-minikube --type=NodePort --port=8080```

Get details of all the services running
```kubectl get services```

Starts a demo-minikube pod
```minikube service demo-minikube --url```

Deleting the minikube services
```kubectl delete service demo-minikube```

Deleting the minikube deployments
```kubectl delete deployment demo-minikube```