# muva-robotics

> This guide is written in 2024, check a more up-to-date installation instructions in the official docs: \
> [Official docs](https://jderobot.github.io/RoboticsAcademy/user_guide/)

## Installing

### Docker
> Make sure you have Docker and WSL2 (in case of Windows) installed and working.

After installing Docker Desktop, make sure the WSL2 integration is ready by enabling this toggle option.
![image](https://github.com/Dokest/muva-robotics/assets/35165785/2eb46b97-a4ab-4337-a67f-20d92310922a)


When Docker is correctly installed, install the following Docker image:
```bash
docker pull jderobot/robotics-academy:4.4.31
```

After the image is downloaded and installed, you can run it using:

```bash
docker run --rm -it -p 7164:7164 -p 2303:2303 -p 1905:1905 -p 8765:8765 -p 6080:6080 -p 1108:1108 -p 7163:7163 jderobot/robotics-academy:4.4.31
```

### Enable GPU processing (NVIDIA)
To enable GPU processing in NVIDIA cards, download the `NVIDIA Container Runtime` from the following [link](https://nvidia.github.io/nvidia-container-runtime/).
Then run this command:

```bash
apt-get install nvidia-container-runtime
```

Verify the installation was successfull using:

```bash
which nvidia-container-runtime-hook
```

When the GPU processing is enabled, you can use the following command to run the Docker image with the GPU enabled:

```bash
docker run --rm -it --gpus all --device /dev/dri -p 7164:7164 -p 2303:2303 -p 1905:1905 -p 8765:8765 -p 6080:6080 -p 1108:1108 -p 7163:7163 jderobot/robotics-academy
```

