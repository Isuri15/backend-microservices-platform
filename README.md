# Backend: Microservices Platform Repository

Parent repository containing the core platform components for the Pet Clinic microservices system, linked as Git submodules.

## Student Information
- **Student Name:** Isuri Gamage
- **Student Number:** 241722008
- **Slack Handle:** 
- **GCP Project ID:** 

## Project Description
This is the parent repository for the platform level infrastructure components of the Pet Clinic microservices system. It links three independent repositories as Git submodules: the Service Registry, the Config Server, and the API Gateway. These components together form the backbone that enables service discovery, centralized configuration, and unified routing for the business microservices.

## Technology Stack
- **Language:** Java 25
- **Framework:** Spring Boot, Spring Cloud
- **Build Tool:** Maven
- **Cloud Platform:** Google Cloud Platform (GCP) — deployed as IaaS on Compute Engine, with multi-zone high availability
- **Process Management:** PM2
- **Repository Structure:** Polyrepo with Git Submodules

## Submodules
| Component | Description | Repository |
|-----------|-------------|------------|
| `eureka-server` | Service Registry — enables service registration and discovery | [eureka-server](https://github.com/Isuri15/eureka-server) |
| `config-server` | Centralized configuration server | [config-server](https://github.com/Isuri15/config-server) |
| `api-gateway` | Single entry point routing requests to backend microservices | [api-gateway](https://github.com/Isuri15/api-gateway) |

## Setup / Getting Started

### Cloning with Submodules
```bash
git clone --recurse-submodules https://github.com/Isuri15/backend-microservices-platform.git
```

If already cloned without submodules:
```bash
git submodule update --init --recursive
```

### Run Order
Start the platform components in the following order before starting the business microservices:
1. `eureka-server` (port 8761)
2. `config-server` (port 8888)
3. `api-gateway` (port 8080) — start this **after** the business microservices are running, so routes resolve correctly

Refer to each submodule's own README.md for detailed setup instructions.

## Cloud Deployment
All three platform components are deployed on Google Cloud Platform using an IaaS model (Compute Engine VM Instance Groups), with multiple instances distributed across different zones within the region to satisfy the high-availability requirement.

## Related Repositories
- [backend-services](https://github.com/Isuri15/backend-services) — business microservices (owner, pet, appointment)
- [frontend-web-app](https://github.com/Isuri15/frontend-web-app) — frontend application
