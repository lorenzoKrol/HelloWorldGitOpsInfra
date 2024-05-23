# Helm Lint Testing GitHub Action

This GitHub Action performs Helm lint testing on your Helm charts to ensure they adhere to best practices and standards.

## How It Works

1. **Set Up Helm**: The action sets up Helm using the `azure/setup-helm@v4.2.0` action with the specified version.
2. **Set Up Python**: The action sets up Python using the `actions/setup-python@v5` action, which is required for the `chart-testing` tool.
3. **Set Up Chart-Testing**: The action sets up the `helm/chart-testing-action@v2.6.0` action to enable Helm chart testing.
4. **List Changed Charts**: The action lists the Helm charts that have changed using `ct list-changed` and sets an output variable if there are changes.
5. **Lint Changed Charts**: If there are changed charts, the action runs `ct lint` to lint the Helm charts.