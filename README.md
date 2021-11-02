# V504 BigData 
Repository for data manipulation examples.

# Installation
In order to use this repository you need to do two things.
- install [docker](https://www.docker.com/get-started)
- open a terminal and `cd` into this GitHub directory
## Docker
```console
docker build -t bigdata:1.0 .
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp bigdata:1.0 
```
# Repository Structure
In the `scripts` directory you can find jupyter notebooks with examples regarding dataframe processing, as well as examples how to interact with NCBIs EDirect software suite and the BLAST commandline tool.
