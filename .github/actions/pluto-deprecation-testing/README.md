# Pluto Helm Deprecation Testing GitHub Action

This GitHub Action performs Helm deprecation testing using Pluto to identify deprecated APIs in your Helm charts.

## Inputs

- `environment` (required): The target environment for which to run the deprecation testing.

## How It Works

1. **Download Pluto**: The action downloads Pluto using the `FairwindsOps/pluto/github-action@master` action.
2. **Run Pluto**: The action uses Pluto to detect deprecated APIs in the Helm charts for the specified environment by running `pluto detect-files -d charts/${{ inputs.environment }}`.