
# Project: Coworking Space Service

The Coworking Space Service is a set of APIs that enables users to request one-time tokens and administrators to authorize access to a coworking space.
## Documentation
Technologies used: Docker, Kubernetes, Github, Aws Codebuild, AWS Elastic Container Registry, Elastic Kubernetes Service


When chanced are made and pushed into Github repository, a build process is triggered on AWS CODE Build which build the Analytics Service into a Docker Image and pushes the image into Elastic Container Registry.

The link to the image is referenced in the kubernetes deployment config file- coworking.yaml.

The database Service and the Analytics service can be started by running command:  kubernetes apply -f deployments/






## Stand-Out Suggestions

Using t3.medium memory of 45% usage and 2%  CPU utilization was achieved. As a result, resource request can be set to 1843Mi of memory which is 45% of 4 GiB (4 GiB * 0.45 = 1.8 GiB, rounded to 1843 MiB) and a cpu usage of 40 millicores derived from 2% of 2 vCPUs (2 vCPUs * 0.02 = 0.04 vCPUs, which is 40 millicores)


Based on the current usage you provided, t3a.small would be more suitale for the clusters. It provides sufficient CPU and just enough memory (2 GiB) while being more cost-effective than the t3.medium.

Costs can be saved by using the recommended instnace type (t3a.small) and configuring the kubernetes to give room for scalling up when CPU or memory utilization goes up.
