**Container Registry**
```
https://docs.docker.com/engine/install/ubuntu/
```

**Dockerfile**
```
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY . .
EXPOSE 80
ENTRYPOINT ["dotnet", "container-test.dll"]
```

**see all the container images in your system**
```
sudo docker images
```

**build the container image from the Dockerfile**
```
sudo docker build -t nameOFtheImageWhateverUwant .
```
you need to be in the same directory where the Dockerfile is.


**To run the docker container image**
```
sudo docker run --name appnginx -p 80:80 -d nginx
```
--name appnginx   => name of the container is appnginx
-p 80:80          => mapping port of container 80 to the vm-port 80
-d                => to run as daimon process
nginx             => name of the image we want to download, install and run on our machine


**see the docker container-images running currently**
```
sudo docker ps
```

**Important Workflow Commands**
```
sudo docker image rm nameOfimage**OR**First3charactersOFtheReference
sudo docker stop nameOfimage**OR**First3charactersOFtheReference
```


**Azure Container Registry (priavately host our container image on AZURE-container-Registry)**
setup AZURE CLI in linux system: ``` https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt ```
azure cli login: ```https://learn.microsoft.com/en-us/cli/azure/acr?view=azure-cli-latest#az-acr-login ```

```
sudo az acr login --name nameOfContainerRegistryCreatedonAzure --username nameFromAccessKeys --password passwordFromAccessKeysOnAzure
sudo docker tag nameOFimagewhateverUwant loginServerFROMazureContainerRegistryAccessKeys/nameOFimagewhateverUwant 
sudo docker push loginServerFROMazureContainerRegistryAccessKeys/nameOFimagewhateverUwant 
```






