| install IIS from SERVER MANAGER |

**Inbound port rules**
80 Http, 8172 for Remote Connection, 


**FOR LINUX VM**
| Configure DNS name |
| have PuTTy, WinSCP softwares in case of Linux VM |

Just encountered on Ubuntu 22.04.
```
sudo apt install aspnetcore-runtime-6.0=6.0.8-1 dotnet-apphost-pack-6.0=6.0.8-1 dotnet-host=6.0.8-1 dotnet-hostfxr-6.0=6.0.8-1 dotnet-runtime-6.0=6.0.8-1 dotnet-sdk-6.0=6.0.400-1 dotnet-targeting-pack-6.0=6.0.8-1
```
Looks like it's a version mismatch between the Ubuntu repos and Microsoft repos.

| dotnet yourApp.dll |

```
sudo apt-get install nginx
sudo service nginx stop
```

| sudo chmod 777 default |
| set config in defaults named file at /etc/nginx/sites-available | as:
```
location / {
		# First attempt to serve request as file, then
		# as directory, then fall back to displaying a 404.
		proxy_pass		http://localhost:5000;
		proxy_http_version	1.1;
		proxy_set_header	Upgrade $http_upgrade;
		proxy_set_header	Connection keep-alive;
		proxy_set_header	Host $host;
		proxy_cache_bypass	$http_upgrade;
	}
```
| sudo chmod 644 default |

sudo service nginx start

