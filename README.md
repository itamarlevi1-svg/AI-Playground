# AI Playground

Personal workspace for experimenting with AI development tools.

## Continuous integration

GitHub Actions runs `experiment.ipynb` from scratch on Python 3.15 for every
push and pull request. A cell error fails the check. You can also start it
manually from the Actions tab using **Run workflow**.

Save the notebook before committing it. CI executes the code saved in Git,
independently of any outputs or running kernel in VS Code.

Dependencies for CI are listed in `requirements-ci.txt`.
Deployment (CD) will be added when the project has a deployment target.
