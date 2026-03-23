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