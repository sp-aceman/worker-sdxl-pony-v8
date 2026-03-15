<div align="center">

<h1>Pony Diffusion XL | Worker</h1>

🚀 | RunPod implementation of SDXL for serverless deployment.  
Forked and modified for to use Pony diffusion
</div>

## Differences from orginal repo

- Change the model to be used from Stable Diffusion XL to Pony Diffusion V8
- Remove the refiner code as Pony Diffusion does not use it
- Remove the use of a seperate VAE as Pony Diffusion does not require it

## 📖 | Getting Started

1. Clone this repository.
2. (Optional) Add DockerHub credentials to GitHub Secrets.
3. Add your code to the `src` directory.
4. Update the `handler.py` file to load models and process requests.
5. Add any dependencies to the `requirements.txt` file.
6. Add any other build time scripts to the`builder` directory, for example, downloading models.
7. Update the `Dockerfile` to include any additional dependencies.

### CI/CD

This repository is setup to automatically build and push a docker image to the GitHub Container Registry. You will need to add the following to the GitHub Secrets for this repository to enable this functionality:

- `DOCKERHUB_USERNAME` | Your DockerHub username for logging in.
- `DOCKERHUB_TOKEN` | Your DockerHub token for logging in.
- `DOCKERHUB_REPO` | The name of the repository you want to push to.
- `DOCKERHUB_IMG` | The name of the image you want to push to.

The `CD-docker_dev.yml` file will build the image and push it to the `dev` tag, while the `CD-docker_release.yml` file will build the image on releases and tag it with the release version.

The `CI-test_worker.yml` file will test the worker using the input provided by the `--test_input` argument when calling the file containing your handler. Be sure to update this workflow to install any dependencies you need to run your tests.

## 🔗 | Links

🐳 [Docker Container](https://hub.docker.com/r/runpod/ai-api-sdxl)
[![Runpod](https://api.runpod.io/badge/sp-aceman/worker-sdxl-pony-v8)](https://console.runpod.io/hub/sp-aceman/worker-sdxl-pony-v8)
