# V504 BigData 
Repository for (biological) data manipulation examples with [miniconda](https://docs.conda.io/en/latest/miniconda.html), the European Molecular Biology Open Software Suite [EMBOSS](http://emboss.open-bio.org/), the multiple sequence alignment tool [MAFFT](https://mafft.cbrc.jp/alignment/server/), the maximum likelihood based phylogenetic inference tool [FastTree](http://www.microbesonline.org/fasttree/), [NCBI's Entrez Programming Utilities](https://www.ncbi.nlm.nih.gov/books/NBK25501/?utm_source=blog&utm_medium=referral&utm_campaign=RefSeq-209&utm_term=EUtilities+&utm_content=20211112link2) and [BLAST command line](https://www.ncbi.nlm.nih.gov/books/NBK279690/) applications. The applications used in this repository are wrapped in a [Docker](https://www.docker.com/get-started) image. All examples and scripts can be viewed with the [jupyter notebook](https://jupyter.org/) interface after building the Docker container as described in the installation section. 

Python offers several packages for data manipulation such as [pandas](https://pandas.pydata.org/), [numpy](https://numpy.org/) and for biological data [biopython](https://biopython.org/), as well as data visualization software such as [Matplotlib](https://matplotlib.org/) and [Altair](https://altair-viz.github.io/). Together with the provided bioinformatic tools, the Docker image can be used as a hub for bioinformatic data manipulation.

However, you do not need to have an active installation of Docker on your system to view and use the Jupyter Notebook files. Simply open those files with your own Jupyter Notebook installation, just make sure to have the modules installed, which are listed by the `import` statements in the header section of the relevant scripts. Some scripts and code begin with the `!` sign. Execution of those code cells may not work for local Anaconda Installations, because you need to have the right software installed on your operating system.
# Installation
In order to use the applications used in the examples of this course you can do the follwing things.
 - install [docker](https://www.docker.com/get-started)
 - download this GitHub repository, either as a ZIP compressed archive or via the `git` command line tool
   -  on this website click on the upper right `code` button and on `Download ZIP` extract the repository into a directory of your choice
   -  if you are experienced with `git`, clone this repository into a directory of your choice
 - open/start a terminal - for windows users: start the `powershell`
   - press `windows + x` and click on `windows PowerShell`
 - navigate into the corresponding directory with the `cd` argument e.g. `cd ~/Documents/` or `cd "C:\Users\XYZ\Documents\GitHub_Directory\big_data"` - you need to put the " signs between your filepath if there are spaces in the directory names - and follow the next instructions
   - alternatively open your filemanager and navigate into this GitHub folder
 - now you are ready to download the docker image with `docker pull` or build it from scratch (`docker build`) with the provided Dockerfile
 - in a last step you can start a docker container with the `docker run` command

If you just want to view the examples and execute python code you can simply open the Jupyter Notebook files with your Jupyter Notebook application.
## BigData Image and Container Setup
> **_NOTE:_** Execute the following code within an terminal/PowerShell pointing at a local copy of this GitHub repository!

You can build the docker image from scratch with the provided `Dockerfile`:
```terminal
docker build -t bigdata:1.0 .
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp bigdata:1.0 
docker exec -it bigdata /bin/bash
```
OR you can simply `docker pull` the image from my [DockerHub](https://hub.docker.com/r/kanomble/bio_big_data_tools) public available builds 
```terminal
docker pull kanomble/bio_big_data_tools:1.4
docker run -dt --name bigdata -v ${PWD}:/BigData/applications -p 127.0.0.1:8888:8888/tcp kanomble/bio_big_data_tools:1.4
docker exec -it bigdata /bin/bash
```
The variable `${PWD}` defines your current filepath. For my personal `document` folder on my windows machine this is: `C:\Users\Lukas Becker\Documents`. `${PWD}` can get replaced with the full length filepath that points to the (downloaded) content of this GitHub repository, e.g. `C:\Users\XYZ\Documents\GitHub_Directory\big_data`.

## Jupyter Notebook

### Container Notebook
Type `http://127.0.0.1:8888/` into your browser, in order to access Jupyter Notebook. If you need to type in a token or a password open a terminal or a PowerShell and submit the command `docker exec -it bigdata /bin/bash`. If your prompt changed to something like this: `root@xyz1234xyz:/BigData/applications`, you have access to the container. Now you can view your running jupyter notebook kernels by submitting the command: `jupyter notebook list`. Copy the link and paste it into your browser search bar. Now you have access to your container's jupyter notebook installation.

### Native (Anaconda) Notebook
Open a terminal/PowerShell and `cd` into the directory of this GitHub repository. E.g. `cd "C:\Users\XYZ\Documents\GitHub_Directory\big_data"` (for windows users), type `jupyter notebook` into your terminal/PowerShell. This will start the `jupyter` application and notebook kernels, which can now be accessed through your browser by typing: `http://127.0.0.1:8888/` into the searchbar.

# Repository Structure
In the `scripts` directory you can find jupyter notebooks with examples regarding dataframe processing, as well as examples how to interact with NCBIs EDirect software suite and BLAST commandline tool. The `data` directory can be used to store data and script results.

# Useful Links
- python [tutrial](https://www.w3schools.com/python/default.asp)
- markdown [cheat sheet](https://www.markdownguide.org/basic-syntax/)
- [emojies](https://emojipedia.org/objects/) for markdown 
- search fields descriptions and tags for [E-utilities](https://pubmed.ncbi.nlm.nih.gov/help/#search-tags)
