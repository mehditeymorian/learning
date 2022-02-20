# OpenShift CLI

## Namespaces (Projects)
shows list of namespaces that you are part of. 
```shell
oc project list 
```

## Select a Namespace (Project)
```shell
oc project [PROJECT-NAME]
```

## Get Resources
**Note**: This command returns all the resources in the namespace.
```shell
oc get all
```

## Create a Resource
```shell
oc apply -f [RESOURCE-FILE-NAME].yaml
```

## Get different Resources
```shell
# return pods
oc get pods
# return statefulsets
oc get statefulsets
# return services
oc get svc
# return deployments
oc get deploy
# return replica sets
oc get replicaset
# return ingresses
oc get ingress
```
**Note**: You can specify a name after the resource type to get a specific resource.

## Describe a resource
give you general information about the resource
```shell
oc describe [RESOURCE-TYPE] [RESOURCE-NAME]
# for example
oc describe statefulset worker-0
```

## Pod Logs
```shell
oc logs [POD-NAME] 
```

## Scaling
Scaling ReplicaSet and StatefulSet
```shell
# scaling replicaSet
oc scale rs/[REPLICA-SET-NAME] --replicas=[NUMBER]
# scaling statefulSet
oc scale sts [STATEFUL-SET-NAME] --replicas=[NUMBER]
```
**Note**: you can use full name for resources' type also. `rs -> replicaset`


## edit quota
```shell
oc edit quota
```

## Team resources
```shell
oc describe appliedclusterresourcequota
```

