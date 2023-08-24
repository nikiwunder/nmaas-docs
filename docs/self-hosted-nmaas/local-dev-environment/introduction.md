# Introduction to the Local Development Environment

Network management is an essential part of any production network, no matter its size. However, organizations often face staff shortages or lack the required resources to properly monitor their network. NMaaS (Network Management as a Service) is a GÉANT production service that allows effortless deployment of many open-source network monitoring tools on demand, with minimal initial configuration by the end users. Based on the Kubernetes container orchestrator, and deployable on private infrastructure as well, a dedicated NMaaS instance can be used as a central point for monitoring many distributed networks, by utilizing VPN tunnels. New applications can be added to the NMaaS catalogue at any time using Helm charts, an industry standard package manager for Kubernetes. NMaaS hides the operational complexity from end users who access the service through a web application from where they can manage and configure their existing application instances or deploy new ones.

Users can also evaluate NMaaS on their own infrastructure by either following this tutorial or by simply [downloading the already prepared virtual machine](https://drive1.demo.renater.fr/index.php/s/rp2awZ6sMnNFQwK). After downloading the virtual machine image, users are advised to follow [part 1](part1.md) in order to set up the necessary VirtualBox NAT network which is required by the VM so that all of its components can run as expected, and the subnets described in the [Appendix](appendix.md) remain unchanged.

By the end of this 5 part tutorial, users should have an exact replica of the setup done within the virtual machine.

This tutorial begins with [part 1](part1.md) where a local Kubernetes cluster is initialized allowing users to choose between two lightweight Kubernetes distributions - MicroK8s or K3s. It then proceeds with [part 2](part2.md) where the NMaaS installation procedure is explained, along with all required dependencies. In [part 3](part3.md), a simple method is described for setting up virtualized demo networking devices that can later be used as monitoring targets for the applications deployed by NMaaS. The process of deploying such monitoring applications from the list of supported applications in the NMaaS catalog is described in [part 4](part4.md). The tutorial is concluded with [part 5](part5.md), allowing advanced users to add their own custom applications to the NMaaS catalog, thus making it available to all potential users of their NMaaS instance.

For users who choose to download the already prepared virtual machine and avoid the whole setup process, the [Appendix](appendix.md) gives an overview of all the credentials that have been used.