# A docker container for AOSP build
A docker container base on ubuntu for AOSP build. It can solve the problem that
the old AOSP cannot be compiled on the latest ubuntu. Tools commonly used to
compile AOSP are integrated in the container. It uses useradd to create the
same user in the container as the host, the default password is **admin**. This
can prevent the host from being unable to access the compiled products in the
container.

## Support version
* ubuntu 16.04
* ubuntu 18.04
* ubuntu 20.04
* ubuntu 22.04

## Build
```shell
git clone https://github.com/RedLeavesSun/android-build-env.git
cd android-build-env
docker build --build-arg USER=${USER} -t aosp-build:<tag> -f <docker file> .
```

## Run
```shell
cd <your project>
docker run -it -v `pwd`:/prj -u 1000 aosp-build:<tag>
```
