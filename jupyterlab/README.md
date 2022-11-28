# Try JupyterLAB on your own machine

## Create a folder where your work will persist

```bash
mkdir -p ./work
```

## Execute the container

```bash
docker run -v ./work:/home/jovyan/work -p 8888:8888 ghcr.io/sosc-school/sosc22-jupyterlab jupyter lab
```

Now you can go directly to the last URL printed in the output to login into the jupyterlab web interface
