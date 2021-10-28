# Follow the guide on [Docker](https://docs.docker.com/samples/rails/)



## Things I had to change
I had to modify the original Dockerfile from the tutorial because of a windows specific issue with postgres not allowing ownership of volume storage. [ANSWER](https://stackoverflow.com/questions/49148754/docker-container-shuts-down-giving-data-directory-has-wrong-ownership-error-wh).




Ensure Hyper-V is enabled on windows desktop.
What I normally run in an administrator powershell is
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```

You must enable file sharing between the host and the container.
A windows notification popped up when I needed to do this.
However, the process can timeout and stop the build process.
If this happens, just check the directories are shared in the Docker desktop app settings and rerun the command 


```
docker-compose run --no-deps web rails new . --force --database=postgresql
```

