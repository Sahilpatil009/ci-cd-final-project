# CI/CD Final Project: Hit Counter Microservice Pipeline

This repository contains the complete Continuous Integration and Continuous Delivery (CI/CD) implementation for the **Hit Counter Microservice** as part of the Coursera **CI/CD Tools and Practices** course (IBM DevOps and Software Engineering Professional Certificate).

## Project Overview

- **Project Name:** Hit Counter Microservice CI/CD Pipeline
- **Repository:** `ci-cd-final-project`
- **Application:** RESTful Flask-based Hit Counter API service
- **CI Tool:** GitHub Actions (`.github/workflows/workflow.yml`)
- **CD Tool:** OpenShift Pipelines / Tekton (`.tekton/tasks.yml`, `pipeline.yaml`)

## Features & Implementation

1. **Continuous Integration (GitHub Actions):**
   - Automatically triggered on code push and pull requests to `main`.
   - Python 3.9 test environment setup.
   - Code linting using `flake8` to enforce PEP8 standards and code quality.
   - Automated unit tests and test coverage using `nosetests` and `coverage`.

2. **Continuous Delivery (OpenShift Pipelines / Tekton):**
   - Workspace cleanup task (`cleanup`) to purge previous build artifacts.
   - Git repository checkout (`git-clone`).
   - Linter task (`flake8`).
   - Unit testing task (`nose`).
   - Container image build using `buildah` ClusterTask.
   - Deployment to Red Hat OpenShift cluster.

## Local Setup

To run this project locally, execute the setup script:

```bash
bash bin/setup.sh
```

Then exit and start a new shell to activate the Python virtual environment:

```bash
exit
```

### Running Tests Locally

```bash
nosetests -v --with-spec --spec-color
```

### Running Linters Locally

```bash
flake8 service
```

## License

Licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.

## Author

Sahil Balasaheb Patil  
IBM Skills Network Learner
