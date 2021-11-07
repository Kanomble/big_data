# V504 BigData 
Repository for data manipulation examples.

# Installation
In order to use this repository you need to do two things.
 - install [docker](https://www.docker.com/get-started)
 - download this GitHub repository, either as a ZIP compressed archive or via the `git` command line tool
   -  on this website click on the upper right `code` button and on `Download ZIP` extract the repository into a directory of your choice
   -  if you are experienced with `git`, clone this repository into a directory of your choice
 - open/start a terminal - for windows users: start the `powershell`
   - press `windows + x` and click on `windows PowerShell`
 - navigate into the corresponding directory with the `cd` argument e.g. `cd ~/Documents/` and follow the next instructions
   - alternatively open your filemanager and navigate into this GitHub folder
 - now you are ready to download the docker image with `docker pull` or build it from scratch (`docker build`) with the provided Dockerfile
 - in a last step you can start a docker container with the `docker run` command
## BigData Image and Container Setup
You can build the docker image from scratch with the provided Dockerfile.
```console
docker build -t bigdata:1.0 .
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp bigdata:1.0 
docker exec -it bigdata /bin/bash
```
OR you can simply `docker pull` the image from my [DockerHub](https://hub.docker.com/r/kanomble/bio_big_data_tools) public available builds 
```console
docker pull kanomble/bio_big_data_tools:1.2
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp kanomble/bio_big_data_tools:1.2
docker exec -it bigdata /bin/bash
```
# Repository Structure
In the `scripts` directory you can find jupyter notebooks with examples regarding dataframe processing, as well as examples how to interact with NCBIs EDirect software suite and BLAST commandline tool. The `data` directory can be used to store data and script results.

