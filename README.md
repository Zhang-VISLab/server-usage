# Server-usage

Vislab is committed to applying deep learning models in computer vision area.

Vislab has three GPU servers under Worcester Polytechnic Insititute sub net, which can provide strong computational ability for deep learning training and test.

## Log in
There are two options for connecting to Vislab server
* Connect to WPI campus Wifi(on campus)
* Connect to WPI VPN(remote), you can download [here](https://hub.wpi.edu/software/570/globalprotect) and find the configuration [here](https://sirloin.wpi.edu/article/23/vpn-client-configuration-for-windows)

``` bash
ssh <usrname>@<vislab-x>.wpi.edu
password
```

## Usage

### View all existing docker image
```bash
docker image ls
```

### Download new docker image
View all docker image in [docker hub](https://hub.docker.com/).

Follow the instruction to pull the image in the server.
```bash
docker pull <repository>:<tag>
```

### Activate a docker container
```bash
docker run --gpus=all -it --name <container name> --shm-size 8G --mount type=bind,source=<absolute path>,target=/workspace <repository>:<tag>
```
*User name* **must be included** in *container name*.

### Exit a container
```bash
exit
```
Docker will **stop** if you run the exit command.
  
## Basic syntax for container

### Check all containers
```bash
docker container ls -a
```

### Start a container
```bash
docker start <container name>
```

### Attach a container
```bash
docker attach <container name>
```

### Stop a container
```bash
docker stop <container name>
```

### Remove a container
```bash
docker rm <container name>
```

## GPU usage

### Check available GPUs
```bash
nvidia-smi
```

### Run your code
```bash
CUDA_VISIBLE_DEVICES=<GPU-index1>, <GPU-index2> <script>
```
GPU index starts from **0**

  


  
