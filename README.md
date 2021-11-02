# V504 BigData 
Repository for data manipulation examples.

# Installation
In order to use this repository you need to do two things.
 - install [docker](https://www.docker.com/get-started)
 - open a terminal, navigate into the corresponding directory and follow the next instructions
## Docker
```console
docker build -t bigdata:1.0 .
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp bigdata:1.0 
docker exec -it bigdata /bin/bash
```
OR
```console
docker pull
docker exec -it bigdata /bin/bash
```
Within the docker container execute following commands:
```console
cd ..
nquire -dwn ftp.ncbi.nlm.nih.gov entrez/entrezdirect xtract.Linux.gz
gunzip -f xtract.Linux.gz
chmod +x xtract.Linux
mv xtract.Linux edirect/
cd applications/
```
# Repository Structure
In the `scripts` directory you can find jupyter notebooks with examples regarding dataframe processing, as well as examples how to interact with NCBIs EDirect software suite and the BLAST commandline tool.
