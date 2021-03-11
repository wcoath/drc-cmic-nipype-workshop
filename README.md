# DRC-CMIC Workshop: Creating processing pipelines with Nipype

## Docker Desktop
If you wish to follow along or play around with Nipype aferwards, you need to install [Docker Desktop](https://www.docker.com/products/docker-desktop).

Once Docker Desktop is installed, open a terminal and run the following command:

`docker run hello-world`

## Download the content

Next, download the workshop docker 'image' it has all the software dependencies and data ready to go.

It is just over 4GB in size:

`docker pull wcoath/nipype_workshop`

## Using Jupyter Notebooks to access the workshop

Everything you do within this docker container will be deleted the moment you terminate the docker run ... command or you close the terminal running it. 

To keep your changes, either manually download the changed notebooks (i.e. File > Download As > Notebook (.ipynb)) or (2) create a common folder within the container and on your system and allow a direct transition of data. To open the container with Jupyrer notebooks with a folder to save your output:

1. Create a folder somewhere on your system called 'my_output'

2. Run this command:

`docker run -p 8888:8888 -it --rm -v /path/to/my_output:/home/neuro/my_output wcoath/nipype_workshop`

Full explanation of command
'docker run' **start up a container already built or pulled**
'-p 8888:8888' **port used local port:container port**
'-it' **run Docker interactively**
'--rm' **remove the container when it exits**
'-v /path/to/my_output:/home/neuro/my_output' **use local files local path:container path**
'wcoath/nipype_workshop' **use specified user/project:version container**

3. Then paste the link given into a web browser to access via Jupyter Notebook.

4. Click on the example pipeline script inside: suvr_analysis_workshop.ipynb

