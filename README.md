# springboot-grpc-template

Example Backstage template for creating a backend Java service running an HTTP server
with Spring Boot.

## Usage

This template will create a new barebones Java service which exposes a sample HTTP endpoint.
Additionally, a PR will be sent to the [Flux](https://github.com/spotify-portal-public-demo/flux)
repo which is used to deploy this service using GitOps.

When run, the template will do the following:

- Create a Java project using the given template parameters
- Publish this project to a new GitHub repo in the `spotify-portal-public-demo` org
- Clone the Flux repo
- Add a new set of Flux manifests based on [this template](https://github.com/spotify-portal-public-demo/flux/blob/main/templates/flux-app.yaml)
- Create a PR against the Flux repo with these new manifests
- Register a Backstage component and API for this service

The Java repo contains GitHub Action workflow files which are used both for testing
and building a Docker image for the Java service. The repo also contains Kubernetes
deployment manifests which are used by Flux as well as a sample Grafana dashboard.

### GitHub Permissions

When running a template which includes GitHub actions (like this one), the GitHub Backstage
integration, whether using a Personal Access Token or a GitHub App, will require permission
to read and write GitHub Actions. The PAT or GitHub App can be modified if this permission
does not already exist.
