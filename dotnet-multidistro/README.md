Installing .Net on Ubuntu
--------------------------
* Manual steps for installing .Net on ubuntu

```
wget https://packages.microsoft.com/config/ubuntu/22.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```
* Install the SDK

```
sudo apt-get update && \
sudo apt-get install -y dotnet-sdk-7.0
```
* Install the runtime

```
sudo apt-get update && \
sudo apt-get install -y aspnetcore-runtime-7.0
```
[Refer_Here](https://learn.microsoft.com/en-us/dotnet/core/install/linux-ubuntu) for official docs

Installing .Net on CentOS
--------------------------

* Manual steps for installing .Net on CentOS

```
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```
* Install the SDK

```
sudo yum install dotnet-sdk-7.0
```

* Install the runtime
```
sudo yum install aspnetcore-runtime-7.0
```

[Refer_Here](https://learn.microsoft.com/en-us/dotnet/core/install/linux-centos) for official docs.
