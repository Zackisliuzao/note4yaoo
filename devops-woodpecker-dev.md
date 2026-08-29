---
title: devops-woodpecker-dev
tags: [git, woodpacker]
created: 2026-08-28T17:49:33.823Z
modified: 2026-08-28T17:49:51.146Z
---

# devops-woodpecker-dev

> simple, yet powerful CI/CD engine with great extensibility.

# guide
- pros
  - license: apache2
  - easily create multiple workflows: they can even depend on each other

- cons
  - ?

- features
  - uses docker containers to execute pipeline steps: If you need more than a normal docker image, you can create plugins to extend the pipeline features

- woodpacker vs github-action
  - 自定义执行task的container/vps

- tips
  - ?
# draft

# dev-xp

# more

# docs-woodpacker

## overview

- CI/CD stands for Continuous Integration and Continuous Deployment. It's basically like a conveyor belt that moves your code from development to production doing all kinds of checks, tests and routines along the way. 
  - A typical pipeline might include the following steps: Running tests, Building your application, Deploying your application

- Woodpecker consists of essential components (server and agent) and an optional component (autoscaler).
  - The `server` provides the user interface, processes webhook requests to the underlying forge, serves the API and analyzes the pipeline configurations from the YAML files.
    - Web UI, API, webhook receiver, pipeline scheduler.
  - The `agent` executes the workflows via a specific backend (Docker, Kubernetes, local) and connects to the server via GRPC. Multiple agents can coexist so that the job limits, choice of backend and other agent-related settings can be fine-tuned for a single instance.
    - Executes pipeline workflows via a backend (Docker, Kubernetes, Local).
  - The `autoscaler` allows spinning up new VMs on a cloud provider of choice to process pending builds. After the builds finished, the VMs are destroyed again (after a short transition time).
- the server and the Docker/Kubernetes backends are Linux-centric, while the agent and CLI run on a wider set of operating systems via the Local backend.

- Woodpecker uses a SQLite database by default. For larger instances it is recommended to use it with a Postgres or MariaDB

- 
- 
- 
- 
- 
- 
- 
- 

## docs

- The Workflow section defines a list of steps to build, test and deploy your code. 
  - The steps are executed serially in the order in which they are defined. 
  - If a step returns a non-zero exit code, the workflow and therefore the entire pipeline terminates immediately and returns an error status.
- Woodpecker has integrated support for matrix workflows. Woodpecker executes a separate workflow for each combination in the matrix, allowing you to build and test against multiple configurations.
- A pipeline has at least one workflow. A workflow is a set of steps that are executed in sequence using the same workspace which is a shared folder containing the repository and all the generated data from previous steps.

- files are only shared between steps of the same workflow. 
  - That means you cannot access artifacts e.g. from the build workflow in the deploy workflow. 
  - If you still need to pass artifacts between the workflows you need use some storage plugin (e.g. one which stores files in an Amazon S3 bucket).

- 
- 
- 
- 
- 
- 
- 
- 
