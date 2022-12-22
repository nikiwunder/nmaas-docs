# What is **NMaaS**?

NMaaS is an [open source](https://github.com/nmaas-platform) framework originally developed within the
[GÉANT](https://geant.org/projects/) project for orchestration of on-demand deployment of applications in a
Kubernetes-based cloud environment.

With a simple self-service web interface, NMaaS applications are easily deployed within an isolated tenant environment
assigned to a given institution or team. An application’s lifecycle (configuration updates and re-deployments) is fully
managed following a GitOps approach: a specific Git repository is tightly associated with every deployed application 
and a set of CI/CD pipelines ensure proper re-deployments of the applications following every update on the Git master
branch.