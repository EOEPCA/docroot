# Federated Orchestrator Building Block

A processing 'federation' is a combination of 'processing' building blocks, that are presented through a single interface.
Depending on the federation, it can take care of aspects such as a single login, shared accounting or more advanced capabilities such as distribution of processing workload across the federation.

This concept is also explained in the [federated orchestrator architecture](https://eoepca.readthedocs.io/projects/architecture/en/latest/reference-architecture/federated-orchestrator-BB/)

In practice, 3 cases of federation can currently be set up:

1. a federation of openEO instances
2. a federation of OGC Processes instances
3. a federation that mixes openEO and OGC Processes instances

At time of writing, a concrete implementation exists only for the first case, in the form of the 'openEO aggregator' implementation.
The other cases can be designed and developed as soon as multiple OGC Processes instances with a shared identity provider are available.

## openEO aggregator

See the [documentation for the `openEO Aggregator`](https://open-eo.github.io/openeo-aggregator/){:target="_blank"} which provides full details - including design, installation and usage information.
