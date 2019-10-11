# Kubernetes custom resource definitions

In the Kubernetes API a resource is an endpoint that stores a collection of API objects of a certain kind. For example, the built-in pods resource contains a collection of Pod objects.

A custom resource is an object that extends the Kubernetes API or allows you to introduce your own API into a project or a cluster.

A custom resource definition (CRD) file defines your own object kinds and lets the API Server handle the entire lifecycle. Deploying a CRD into the cluster causes the Kubernetes API server to begin serving the specified custom resource.

When you create a new custom resource definition (CRD), the Kubernetes API Server reacts by creating a new RESTful resource path, that can be accessed by an entire cluster or a single project (namespace). As with existing built-in objects, deleting a project deletes all custom objects in that project.

If you want to grant access to the CRD to users, use cluster role aggregation to grant access to users with the admin, edit, or view default cluster roles. Cluster role aggregation allows the insertion of custom policy rules into these cluster roles. This behavior integrates the new resource into the cluster’s RBAC policy as if it was a built-in resource.


[Link ](https://docs.okd.io/latest/admin_guide/custom_resource_definitions.html)
