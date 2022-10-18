** Container Registry
```
	https://docs.docker.com/engine/install/ubuntu/

```

** Dockerfile
```
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY . .
EXPOSE 80
ENTRYPOINT ["dotnet", "container-test.dll"]
```
