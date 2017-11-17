<<<<<<< HEAD
# Building The General Clustering Pipeline Docker Image

The Dockefile in this directory contains all the commands, in order, needed to build the **General Clustering Pipeline** docker image.

* Run the "make" command to build the **General Clustering Pipeline** docker image (output: docker image called "general_clustering_pipeline" and a tag with today's date and time):
=======
# Building The Samples Clustering Pipeline Docker Image

The Dockefile in this directory contains all the commands, in order, needed to build the **Samples Clustering Pipeline** docker image.

* Run the "make" command to build the **Samples Clustering Pipeline** docker image (output: docker image called "samples_clustering_pipeline" and a tag with today's date and time):
>>>>>>> Signature_Analysis_Pipeline/master
```
    make build_docker_image
```

* Login to docker hub. When prompted, enter your password and press enter:
```
    make login_to_dockerhub username=(enter your docker login here) email=(enter your email here)
```

* Upload your image to docker hub:
```
    make push_to_dockerhub
```

* * * 
## How to run this docker image
* * * 

### 1. Run the following command with the specified docker image:
```
<<<<<<< HEAD
docker run -v `pwd`:/home/test/run_dir/ -it knowengdev/general_clustering_pipeline:07_26_2017
=======
docker run -v `pwd`:/home/test/run_dir/ -it knowengdev/samples_clustering_pipeline:03_15_2017
>>>>>>> Signature_Analysis_Pipeline/master
```

### 2. Change directory to the "test" directory
```
cd test
```

### 3. Create the local directory "run_dir" and place all the run files in it
```
make env_setup
```

<<<<<<< HEAD
### 4. Run the General Clustering Pipeline
```
make run_hclust
=======
### 4. Run the Samples Clustering Pipeline
```
make run_cc_net_nmf
>>>>>>> Signature_Analysis_Pipeline/master
```
