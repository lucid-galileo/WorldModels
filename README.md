# WorldModels

## Docker
The easiest way to handle dependencies is with [Nvidia-Docker](https://github.com/NVIDIA/nvidia-docker). Follow the instructions below to generate and attach to the container.
```
docker image build -t wm:1.0 -f docker/Dockerfile.wm .
docker container run -p 8888:8888 --gpus '"device=0"' --detach -it --name wm wm:1.0
docker attach wm
```

# Instructions for running the pretrained model already in repo

To run model in actual environment 100 times and not visualize the episodes, while computing mean score do the following inside the WorldModelsExperiments/doomrnn directory:

`python model.py doomreal norender tau1.15_log/doomrnn.cma.16.64.best.json`

An evaluation log across 1k episodes on the real doom environment can be found [here](https://github.com/zealous-wescoff/WorldModels/blob/master/WorldModelsExperiments/doomrnn/tau1.15_eval.txt)
