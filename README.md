# Scottish Summit 2021 - Power Platform Actions Demo

The repository demonstrates how to use [Power Platform Actions](https://github.com/microsoft/powerplatform-actions) to do ALM in Power Apps. This repository contains 4 Workflows.

| Workflow Name | Description |
| - | - |
| initialise-repo.yml | Run this workflow manually to "seed" the repo with the solution specified in the workflow dispatch input. |
| commit-solution-components.yml | This is a manual workflow as well, to take the solution from DEV and commit it into a new branch on the repo. This can be a [cron](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#schedule) trigger if you want this to happen every day at a preset time. |
| deploy-solution-ci.yml | This workflow runs anytime files are pushed into Solutions/** on the main branch. It packages up the solution and deploys it into the TEST environment. |
| deploy-solution-manual.yml | This is similar to the previous workflow, except that it can only be run manually. |

All Power Platform Actions use Application Id/Secret to connect to the Dataverse API. The ApplicationId is defined in each individual workflow, and the Application Secret is setup as a secret in the repo level The name of the secret is DATAVERSESECRET.