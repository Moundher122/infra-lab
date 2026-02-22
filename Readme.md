# 🏗 Infrastructure Lab

## 📌 Overview

This project is a structured infrastructure lab designed to simulate how
real-world companies manage multiple environments using Infrastructure
as Code principles.

The lab models three isolated environments:

-   Development
-   Staging
-   Production

All environments share the same infrastructure codebase while using
separate configuration variable files to ensure strict isolation and
reproducibility.

------------------------------------------------------------------------

# 🏛 Architecture Strategy

Instead of separating environments into folders or branches, this
project follows a professional approach used in modern infrastructure
teams:

> One codebase\
> Multiple environment variable files\
> Separate state per environment

This ensures consistency while allowing each environment to behave
independently.

------------------------------------------------------------------------

# 🌍 Environment Model

The environments are managed using different variable files:

    infra/terraform
    │
    ├── main.tf
    ├── variables.tf
    ├── outputs.tf
    │
    ├── dev.tfvars
    ├── staging.tfvars
    └── prod.tfvars

Each environment is applied using:

    terraform apply -var-file=dev.tfvars
    terraform apply -var-file=staging.tfvars
    terraform apply -var-file=prod.tfvars

------------------------------------------------------------------------

# 🧱 Infrastructure Layer

The infrastructure layer is responsible for:

-   Provisioning compute resources
-   Defining networking components
-   Managing isolation between environments
-   Creating reproducible system definitions
-   Maintaining separate infrastructure state per environment

Although the infrastructure logic is shared, each environment has:

-   Different resource sizing
-   Different scaling configuration
-   Different access rules
-   Different environment-specific settings

------------------------------------------------------------------------

# ⚙ Platform Layer

Inside each provisioned environment, a platform layer runs workloads and
orchestrates services.

This layer handles:

-   Workload scheduling
-   Service orchestration
-   Resource allocation
-   Horizontal scaling
-   Environment-specific runtime configuration

Each environment can simulate different levels of traffic and stability
requirements.

------------------------------------------------------------------------

# 🌐 Networking Layer

Networking is environment-aware and isolated.

It includes:

-   Internal service communication
-   Controlled external access
-   Traffic routing rules
-   Environment boundary enforcement

Production networking is expected to be stricter and more controlled
compared to development.

------------------------------------------------------------------------

# 🚀 Services Layer

The services layer contains backend applications and system components
deployed within each environment.

Each environment represents a different lifecycle stage:

-   Development → experimentation and rapid iteration
-   Staging → validation and pre-production testing
-   Production → stable and controlled deployment

The same service version can be promoted across environments to simulate
real-world release workflows.

------------------------------------------------------------------------

# 🔄 Deployment Workflow

This lab simulates a professional promotion pipeline:

1.  Infrastructure changes are defined once.
2.  Development environment is applied and validated.
3.  Changes are promoted to staging for verification.
4.  Production deployment requires controlled execution.

Each environment maintains its own state to prevent cross-environment
impact.

------------------------------------------------------------------------

# 🧠 Architectural Principles

-   Infrastructure as Code
-   Environment isolation
-   Reproducibility
-   Separation of concerns
-   Controlled promotion between environments
-   Production-like simulation

------------------------------------------------------------------------

# 🚀 Long-Term Vision

-   Implement remote state management
-   Introduce approval-based deployment simulation
-   Add monitoring and observability layers
-   Simulate failure and recovery scenarios
-   Improve automation maturity

------------------------------------------------------------------------

# 📚 Status

This is an evolving infrastructure lab designed to reflect real
enterprise patterns for managing multiple environments within a single
infrastructure codebase.