# test-runner

This is a brief repo specific version to the existing docker documentation: [Build and push your first image](https://docs.docker.com/get-started/introduction/build-and-push-first-image/). Refer to [docker documentation](https://docs.docker.com/get-started/introduction/build-and-push-first-image/) for initial steps to create your own docker repository in Docker Hub until reaching the [Build and Push The Image](https://docs.docker.com/get-started/introduction/build-and-push-first-image/#) section in the docker documentation. Then run:
```
git clone https://github.com/ue-shuston/laravel-test-runner
```
to clone this repo to the desired directory in ubuntu.

1. Update or create the needed Dockerfile in this repository.
2. Merge the changes made into the `main` branch.

3. Get into local repository:
```
cd /repositories/laravel-test-runner
```

4. Pull the latest changes from the remote repository:
```
git pull
```

5. Continue into the image needing to be built with the updated docker file ("8.4" in the following example):
```
cd 8.4
```

6. Built the image using your docker username and the desired tag (example tag is also "8.4" in the following example):
```
docker build -t <docker username>/test-runner:8.4
```

Note: Additional tags can be added by appending:
```
-t <docker username>/test-runner:<other tag here>
```
to the command in step 6.

7. Check the docker images on your environment for the one just generated:
```
docker image ls 
```

8. Push the newly generated docker image via the specific tag ("8.4" in the following example):
```
docker push <docker username>/test-runner:8.4
```
