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

Everything you do within this docker container will be deleted the moment you terminate the docker 'run ...' command or you close the terminal running it. 

To keep your changes, either manually download the changed notebooks (i.e. File > Download As > Notebook (.ipynb)) or create a common folder within the container and on your system and allow a direct transition of data. 

To open the container with Jupyrer notebooks with a folder to save your output:

1. Create a folder somewhere on your system called 'my_output'

2. Run this command, filling in the path to the folder you just created:

`docker run -p 8888:8888 -it --rm -v /path/to/my_output:/home/neuro/my_output wcoath/nipype_workshop`

Full explanation of command:

docker run = **start up a container already built or pulled**

-p 8888:8888 = **port used {local port}:{container port}**

-it = **run Docker interactively**

--rm = **remove the container when it exits**

-v /path/to/my_output:/home/neuro/my_output = **use local files {local path}:{container path}**

wcoath/nipype_workshop = **use specified {user}/{project:version} container**

3. Then copy and paste the bottom link from the terminal output into a web browser to access via Jupyter Notebook, the link should look start with this:

http://127.0.0.1:8888/?token= (don't use this link it needs the token at the end)

4. When the notebook has loaded you should have folders for 'data', 'output' and 'my_output' (this is where you can store files you want to keep locally in your 'my_output' folder. Click on the example pipeline script 'suvr_analysis_workflow.ipynb', you can run it and see how it works. It is currently read only, so if you want to edit you can save a copy inside my_output to keep any changes you make.

## Dockerfile & Analysis Script

The Dockerfile I used to build the Docker image for the workshop is included in this repo, if you wish to customise the image you can put this Dockerfile inisde a directory, make your edits and then build from inside the same directory as the Dockerfile using this command:

`docker build -t {your_username}/{image_name} .`

If you want to include any directories/files in your Docker image they need to be in the same directory as the Dockerfile, and in the Dockerfile you can specify lines to ADD or COPY them in.



