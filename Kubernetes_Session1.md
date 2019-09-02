# Kubernetes
*   The Industry 4.0 way of application deployment engine.
*   During 2015-2018 Indeed Job search, Kubernetes 1st Rank Technology.
* Best Devops technology which is used to integrate with lot of stuff.
* It is the product designed by Google
* It is a Orchestration Engine used to manage and schedule containers .
* Google Donated this project to CNCF Company who is manageing kubernates now.

## Packaging of Software
* For example I am building a product called Skype, I will code it first then integrate then test and finally deploy and release the product.
* Packaging means adding up all your project files and combining them in a installable form for specific OS like exe,deb,rpm etc.

### New generation method of packaging
*   In new generation methology we have both code and platform for packaging, Code(exe,py,deb,rpm) platform(OS in docker as platform provider).

## Docker
* Docker is a software which provide us (PAAS) Platform as a service.
* Docker runs on Operating system which uses the base OS kernel for launching a container.
* Simply you can say docker is a code testing and deployment platform.
* To check docker is installed or not
```
dpkg -l | grep -i docker
```
* Docker is somewhere like a VMWare software, but actually not.
* Therefore we need some images of an Operating system.
* Generally when we install multiple platforms in a single operating system like java, python, R etc, and some of thier liberaries crash with eachother as such we cannot use a single OS for testing our code.
### Running a simple sh code in alpine container
```bash
docker run -it --rm -v /root/code:/code alpine sh /code/file.sh
```
*   ```run``` means you are creating a new container or platform.
*   ```-it``` means we need an interactive way to display the output.
*   ```-v /root/code:/code``` this means the 1st path is the main os folder path, and the ```:/code``` is a new folder will create in the container.
*   Basically we are copying/sharing folder like nfs with container.
*   ```alpine``` is the operating system name
*   ```sh``` this is the program which will be used to run a file or program.
*   ```/code/file.sh``` This is the file we copied inside the container and we are running it with sh program.

### Listing and deleting docker containers
```bash
# To list running containers
docker ps
# To list running all containers running or stopped
docker ps -a
# To stop a container use the container_id
docker stop CONTAINER_ID
# To remove a container use the container_id
docker rm CONTAINER_ID
# To remove all containers in one go use ps -aq to list all container_ids
docker rm $(docker ps -aq)
```
### To list and remove images of docker
```bash
# To list all images
docker images
# To remove an image
docker image rm IMAGE_NAME
```
### Running a python code in docker container
```bash
docker run -it --rm -v /root/code:/code python python /code/abc.py
```
*   The best part is whatever we made changes in the base OS files it will copy in realtime inside the container also.

## GO lang
* It was 1st introduced in 2008 - 2009
* In this language we will write allmost everything inside a function.
* In Go we can import a liberary online without installing in your base machine.
* GoLang is both compile and Run
* It dosent dupport dead code

### Go Lang sample code
```go
package main //defining main function
import "fmt"

func main(){
    // This is a dead code because this variable is not been used anywhere in the program
    a:=20 // To create a variable in goLang

    // Fmt have this function for printing a line
    fmt.Println("Hello world, welcome to goLang")
}
```
*   A dead code is a code which is written by the programmer but not been used in the code anywhere.
*   As such goLang wont allow you to execute a  dead code it will simply give an error.
### Simple way to run a go file in docker
```bash
docker run -it --rm -v /root/code:/code golang go run /code/hello.go
```
## Why Kubernetes
*   When we have a lot of containers launching dynamically by users in realtime, we might also get errors and problems with the containers.
* Since we are running 1000's of containers at same time and we need to resolve the errors as such we need to do orchestration.
* Managing each and every container that it will not shutdown or crash this process is called container orchestration.
* In order to do this we need kubernetes with app engine to manage and process container orchestration.
