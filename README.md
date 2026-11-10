# AI Playground

Personal workspace for experimenting with AI development tools.

## Hugging Face experiment

Open `hugging_face_intro.ipynb` in VS Code and choose the project's Python
kernel. The Hebrew walkthrough runs English sentiment analysis locally with
DistilBERT. Dependencies are recorded in `requirements-huggingface.txt`.
The first run downloads the public model to `.hf-cache/`; no API key is needed.
This optional notebook is separate from the CI notebook below.

## Reddit scam research prototype

Open `reddit_scam_research.ipynb` for a Hebrew walkthrough that classifies
English texts by scam type and concern, then summarizes their frequency.
It uses **synthetic examples only**, not live Reddit data. Run the optional
installation cell if needed; dependencies are in `requirements-reddit-scam.txt`.
The model-loading cell downloads a separate zero-shot model to `.hf-cache/`.
Model scores and thresholds require manual validation before drawing conclusions.
Reddit collection and scheduling are future steps, pending approved access.
This optional notebook is not executed by CI.

## Continuous integration

GitHub Actions runs `experiment.ipynb` from scratch on Python 3.15 for every
push and pull request. A cell error fails the check. You can also start it
manually from the Actions tab using **Run workflow**.

Save the notebook before committing it. CI executes the code saved in Git,
independently of any outputs or running kernel in VS Code.

Dependencies for CI are listed in `requirements-ci.txt`.

## Continuous deployment

After CI succeeds on `main`, the same workflow publishes only the `site/`
directory to GitHub Pages. Pull requests run CI without deploying.

One-time setup: in the repository, open **Settings → Pages → Build and
deployment**, and set **Source** to **GitHub Actions** before pushing this workflow.

Commit and push `site/index.html` and the updated workflow. In **Actions**, open
the latest run and check **Publish HTML to GitHub Pages**. The deployment
environment links to the published site. To practice CD, change the heading in
`site/index.html`, commit, and push again.
