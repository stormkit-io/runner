# Stormkit Runner

This repository allows Stormkit to use GitHub actions to run the deployments.

## Configuring Stormkit to use this Repository

Make sure to set the following environments variables for both API and Workerserver Services:

| Environment Variable        | Value                    | Description                                                               |
| --------------------------- | ------------------------ | ------------------------------------------------------------------------- |
| `STORMKIT_DEPLOYER_SERVICE` | `github`                 | Instructs Stormkit to use GitHub Actions.                                 |
| `GITHUB_RUNNER`             | `:namespace/:repository` | The repository name, including namespace/owner (e.g. stormkit-io/runner). |
| `GITHUB_APP_TOKEN`          | `<access-token>`         | A personal access token that grants access to this GitHub repository.     |

## Default Branch

Make sure to use `main` as the default branch for this repository.

## Generating an Access Token

1. Go to github.com
1. Click on your **Avatar** > **Settings**
1. Scroll down and click on **Developer Settings**
1. Expand **Personal Access Tokens**
1. Click on **Tokens (classic)** if you'd like to create a token without expiration
1. Click on **Fine-grained tokens** if you'd like to create a token with expiration

Note: If you're using a **Fine-grained token** make sure to expand `Repository permissions` and
grant `Access: Read and write` to `Actions` item.

## Setting Environments Variables

After having created a new repository by clicking on `Use this template` we need to specify to the
`STORMKIT_APP_SECRET` environment variable to handle encrypted data. To do that:

1. Visit your repository
1. Click on `Settings`
1. On the left navigation menu find and expand **Security** > **Secrets and variables**
1. Click on **Actions**
1. Click on **New repository secret**
1. Create a new secret called `STORMKIT_APP_SECRET` and make sure that it matches the secret used
   by other microservices.

## License

Check out our [License](./LICENSE.md).
