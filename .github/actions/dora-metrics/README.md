# Generate Dora Metrics GitHub Action

This GitHub Action generates Dora metrics for your repository and commits the insights to a specified branch.

## Inputs

- `github_application_repo_commit_username` (required): The username of the account you want to commit with to the infrastructure repository.
- `github_application_repo_commit_user_email` (required): The email of the account you want to commit with to the infrastructure repository.
- `github_access_token` (required): Authorization token for accessing the GitHub API.
- `branch` (required): The branch of the repository where the metrics insights will be committed.

## How It Works

1. **Checkout code**: The action checks out the repository code using the `actions/checkout@v4` action, fetching the entire history to ensure all necessary files are available for generating metrics.
2. **Set up Docker Buildx**: The action sets up Docker Buildx using the `docker/setup-buildx-action@v2` action, allowing for advanced build capabilities.
3. **Pull Docker image**: The action pulls the Docker image `abhimishraa/dorametrics:latest`, which contains the tool for generating Dora metrics.
4. **Generate metrics**: The action runs the Docker container and generates Dora metrics for the repository. The generated metrics are saved to the `metrics` directory. The `--calculate-metrics` flag is used to specify metric calculation, and `-p ${{ inputs.branch }}` is used to specify the branch for which metrics are generated.
5. **Commit files**: The action configures Git user details, adds the generated metrics files, commits them with a message indicating updates to metrics insights.
6. **Push changes**: The action pushes the committed changes to the specified branch using the `ad-m/github-push-action@master` action.