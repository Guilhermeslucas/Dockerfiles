#Dockerfiles

This repository is for publishing the Dockerfiles I have made during my work for
OpenPower Foundation.

Dockerfiles list:
- Jenkins ppc64le
- IBM Development Tools (IBM SDK, XL, Advance Toolchain) - Ubuntu ppc64le 

To build one of these images,go to the directory of the image you want to build and type:
```
$ docker build -t "name you want for the image on owner/tag format" .
```
Note: Don't use uppercase letters for the tag name.
