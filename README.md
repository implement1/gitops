# Configure Synchronization with GitOps

Hero and Lil DeeBee can see it in the distance: production! The air is tingling with excitement. But how will Hero get there? Hero's parent applications/infrastructure were declaratively defined with code just like Hero, and those definitions lived in Git where they could be versioned and tested, just like Hero. However, Hero's parents were likely to be manually deployed, and then updates were triggered by pipelines and webhooks that would run whenever the definition code got updated. That is an improvement over olden times when applications and infrastructure ran imperatively, but still problematic because each step relied on every step before it, which is a fragile, brittle technique that often needs manual intervention if something goes wrong. Another problem is that a human might unknowingly change the running resources directly (for example, use the Google Cloud Platform UI to add a node to a cluster), which would result in the Git definitions being out-of-sync with the resources they're defining, and the error wouldn't get caught until the next time Git is updated. 

Hero has heard the cool kids discussing this idea called GitOps⎯a resource management technique where you declaratively define the desired state of your application deployment, infrastructure, and/or services, store those Kubernetes resource definitions in Git, and then a GitOps tool keeps those Kubernetes resource definitions in sync with the actual state of the real, running resources that are deployed in your Kubernetes cluster. 

It is worth noting here that GitOps tools need to work in tandem with other Kubernetes add-ons to be able to manage resources that are completely outside of a Kubernetes cluster, but it can be done!

There are four [GitOps Principles](https://opengitops.dev/):

1-**Resources Are Defined Declaratively**
A system managed by GitOps must have its desired state expressed declaratively.

2-**Resource Definitions Are Versioned and Immutable**
The desired state is stored in a way that enforces immutability, enforces versioning, and retains a complete version history. Usually, Git is used for this.

3-**Resource Definitions Are Pulled Automatically**
Software agents automatically pull the desired state declarations from the source. Here 'software agents' refers to the GitOps tool and, again, the source is usually Git.

4-**The Desired State Is Continuously Reconciled With the Actual State**
Software agents (GitOps tools) continuously observe the actual system state and attempt to apply the desired state.

## Choice 1: Flux

Explanation

* [Official site](https://fluxcd.io)

## Choice 2: Argo CD

TODO: Explanation

* [Official site](https://argoproj.github.io/cd)

## Choice 3: Carvel Kapp Controller

TODO: Explanation

* [Official site](https://carvel.dev/kapp-controller)

## What Is Your Choice?

* [Flux](flux.md)
* [Argo CD](argocd.md)
* [Carvel kapp-controller](kapp.md)