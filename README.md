BookVerse Example
=================

[//]: <> (FIXME: Give an executive summary here.)

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
