# 1. First we can create an App service plan

```
az appservice plan create --name companyplan
                          --resource-group app-grp
                          --is-linux
```

# 2. Then we create the web app
```
az webapp create --resource-group app-grp
                 --plan companyplan
                 --name dockerapp55000
                 --deployment-container-image-name appregistry1000122.azurecr.io/sqlapp:latest
```

# 3. If you want to turn on container logging
```
az webapp log config --name dockerapp55000
                     --resource-group app-grp
                     --docker-container-logging filesystem
```

# 4. Enable the log stream
```
az webapp log tail --name dockerapp55000
                   --resource-group app-grp
```
