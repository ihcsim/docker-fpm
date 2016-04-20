# docker-fpm
Docker image for FPM (https://github.com/jordansissel/fpm).

## Introduction
FPM is a package management tool that makes creating and updating existing packages (deb, rpm, tar, zip, osxpkg etc.) easy.

For more information, refer https://github.com/jordansissel/fpm

## Getting Started
* To pull: `docker pull isim/fpm`
* To build: `docker build --rm -t isim/fpm .`
* To run: `docker run --rm isim/fpm <fpm-command>`

To create a debian package from a binary located in your current folder:
```sh
$ docker run --rm 
  -v `pwd`:/workspace \
  -w /workspace 
  isim/fpm \
  -s dir \
  -t deb \
  -n $OUTPUT_PACKAGE_NAME \
  -v $PACKAGE_VERSION \
  --deb-no-default-config-files \
  --prefix=/usr/local \
  $PATH_TO_BIN
```


## License
Refer to the [LICENSE](LICENSE) file.
