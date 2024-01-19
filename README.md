# CVE analysis 2

Readme for second CVE analysis

## Setup
Go to the machine subdirectory  
`cd machine`  
Build the docker image as follows  
`docker build . -t devoir2`  
Run the docker container  
`docker run -it --name=devoir2_container --env="DISPLAY" --net=host devoir2`  
Open your browser and reach the address http://localhost:8080/

## Cleanup
Once the process is terminated, type the following commands  
`docker rm devoir2_container`  
`docker image rm devoir2:latest`
