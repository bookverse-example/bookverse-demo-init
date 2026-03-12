BookVerse Example
=================

BookVerse Example is a cloud-native microservices reference application that demonstrates secure software delivery using
the JFrog Platform. Built as an online bookstore, it comprises an Inventory Service for product catalog management, a
Recommendations Service powered by machine learning, a Checkout Service for order processing, a vanilla JavaScript Web
Application, shared Infrastructure Libraries, Helm Charts for Kubernetes deployment, and a Platform Service for
integration testing — each showcasing distinct CI/CD build patterns ranging from single-container deployments to
multi-artifact library publishing.

The project's primary purpose is to provide a complete, end-to-end reference architecture for enterprise-grade software
supply chain security. It leverages JFrog AppTrust with 14 automated policy gates spanning four lifecycle stages (DEV,
QA, STAGING, and PROD), cryptographically signed evidence collection, SLSA provenance verification, and multi-layer
security scanning (SAST, DAST, penetration testing, and IaC). Deployments are managed through GitOps workflows with
ArgoCD, and the entire environment — including JFrog Platform provisioning, GitHub repository creation, and OIDC
integration — can be stood up automatically through the orchestration workflows in this repository.

[What is BookVerse Example?](docs/what_is_bookverse_example.md)

[Indepth Documentation](docs/index.md)

[Getting Started Guide](docs/GETTING_STARTED.md)

[Platform Architecture Overview](docs/ARCHITECTURE.md)

[Demo Runbook](docs/DEMO_RUNBOOK.md)

[AppTrust Showcase Guide](docs/APPTRUST_SHOWCASE_GUIDE.md)

Quick Start
-----------

1. Fork `bookverse-demo-init` repository (this one) to your user or organization.  This repository contains all of the
   actions and script necessary to setup and cleanup the workflows and JFrog Platform.  Only forking this repository is
   required as the first action to run will fork the remaining git repositories.

2. Set necessary secrets for the workflows.  These secrets can be set on the _Settings -> Secrets and variables ->
   Actions_ page in the _Repository Secrets_ section.

   * `JFROG_ADMIN_TOKEN` - An admin level token for the JFrog Platform installation that will be used.

   * `GH_TOKEN` - A GitHub Personal Access Token (PAT) classic with _'repo'_, _'workflow'_, and _'admin:repo_hook'_
                  permissions.  This is required to fork the other repositories and setup the project.

3. Run the _Step 1: Initialize Repositories_ action.  This can be found on the _Actions_ tab.  Use the settings below to
   configure the initial setup run.

   * Setup Mode: `initial_setup`

   * JFrog Platform Host: `https://<JPD_URL>`  This will be the URL for your JFrog Platform.
     e.g. _https://example.jfrog.io_

   * Admin Token: Leave empty as it has been configured in a secret.

   * Confirm Switch: Leave empty as 

   * Generate Evidence Keys: `true`

   * Evidence Key Type: `rsa`  Can be _rsa_, _ec_, or _ed25519_.

   * Evidence Key Alias: `bookverse-signing-key`

   * Update Code URLs: `false` Set this to false to skip this step for the initial run.

   * Update K8s: `false` Set this to false to skip configuring Kubernetes for the initial run.

[//]: <> (FIXME: Should the Platform Host / URL be moved to a secret?)
[//]: <> (FIXME: Should the admin token value be removed and the secret forced?)
[//]: <> (FIXME: What does the Update Code URLs option do?  Should it be removed?)

4. Run the _Step 2: Setup Platform_ action.  This can be found on the _Actions_ tab.  No settings are required for this
   action.

5. Run the _Step 3: Initial Build Actions_ action.  NOTE: THIS DOESN'T EXIST YET!

[//]: <> (FIXME: This should be created to run each of the build actions in each of the sub projects.)


Components
----------

[//]: <> (FIXME: Add a brief summary of each service here.)

**Note**: Individual service documentation is available in each service repository:

* [Checkout Service](https://github.com/bookverse-example/bookverse-checkout)

* [Demo Assets](https://github.com/bookverse-example/bookverse-demo-assets)

* [Helm Charts](https://github.com/bookverse-example/bookverse-helm)

* [Infrastructure Libraries](https://github.com/bookverse-example/bookverse-infra)

* [Inventory Service](https://github.com/bookverse-example/bookverse-inventory)

* [Platform Service](https://github.com/bookverse-example/bookverse-platform)

* [Recommendations Service](https://github.com/bookverse-example/bookverse-recommendations)

* [Web Application](https://github.com/bookverse-example/bookverse-web)
