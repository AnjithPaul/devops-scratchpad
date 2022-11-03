#kubernetes #service
## Service

an abstraction over a set of pods. To access a logical set of pods (e.g: backend pods) create a service abstraction over it and access the service.

### Node port
Creates a server kind of thing inside the node to expose the pod to outside node.

communicate to : `<ip_of_node>:<nodePort>`

`spec:`
	**port**: port of service
	**targetPort**: port of pod
	**nodePort**: port on the node for external access

### Cluster IP
default service type. groups together a set of pods and provide a single interface for other pods to access this set of pods. request goes to a random pod in the set.

communicate to : clusterIP or service Name