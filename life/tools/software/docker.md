# Docker

## Learn Enough Docker to be Useful <a id="4a70"></a>

### Part 1: The Conceptual Landscape <a id="e8e6"></a>

{% embed url="https://towardsdatascience.com/learn-enough-docker-to-be-useful-b7ba70caeb4b" %}

* Docker is a platform to develop, deploy, and run applications inside containers.
* Docker containers are superior to virtual machines because they take fewer resources, are very portable, and are faster to spin up.

### Docker Containers

* Holds things: There are things both inside and outside of a container
* Is portable: Cam be used your local machine, coworker's machine or on the cloud
* Has clear interfaces for access: Configure to interact through the command line
* Can be obtained from a remote location: Registry keeps an image which can create containers on demand
* Docker container is a Docker image brought to life
* Superior to virtual machines because containers take fewer resources, are very portable, and are faster to spin up

### Docker Image

* An image contains the Dockerfile, libraries, and code your application needs to run, all bundled together
* `docker run image_name` creates and starts a container from an image

### Dockerfile

* A recipe file with instructions for how Docker should build your image
* Base image layer: Used to build the initial image layer
  * Example: ubuntu, node
* Additional layers can then be stacked on top of the base image layers
  * Example: Libraries such as alfresco-content-repository, es6-angular-webpack
* Thin writable layer

### Container Registry

* Share your image with others
* [Docker Hub](https://hub.docker.com/) is the largest registry

### Part 2: A Delicious Dozen Docker Terms You Need to Know <a id="c38b"></a>

[https://towardsdatascience.com/learn-enough-docker-to-be-useful-1c40ea269fa8](https://towardsdatascience.com/learn-enough-docker-to-be-useful-1c40ea269fa8)

### Part 3: A Dozen Dandy Docker file Instructions <a id="c38b"></a>

[https://towardsdatascience.com/learn-enough-docker-to-be-useful-b0b44222eef5](https://towardsdatascience.com/learn-enough-docker-to-be-useful-b0b44222eef5)

### Part 4: Slimming Down Your Docker Images <a id="c38b"></a>

[https://towardsdatascience.com/slimming-down-your-docker-images-275f0ca9337e](https://towardsdatascience.com/slimming-down-your-docker-images-275f0ca9337e)

### Part 5:15 Docker Commands You Should Know <a id="c38b"></a>

[https://towardsdatascience.com/15-docker-commands-you-should-know-970ea5203421](https://towardsdatascience.com/15-docker-commands-you-should-know-970ea5203421)

### Part 6: Pump up the Volumes: Data in Docker <a id="c38b"></a>

[https://towardsdatascience.com/pump-up-the-volumes-data-in-docker-a21950a8cd8](https://towardsdatascience.com/pump-up-the-volumes-data-in-docker-a21950a8cd8)





