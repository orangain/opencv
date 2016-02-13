# PPA of OpenCV 3.0

This is a PPA of OpenCV 3.0 for Ubuntu trusty ported from [Debian's experimental OpenCV 3.0 package](https://packages.debian.org/experimental/python-opencv). Also provide the python3-opencv package.

Original README.md is available at [README.orig.md](https://github.com/orangain/opencv/blob/python3/README.orig.md).

## Usage

```
$ sudo add-apt-repository ppa:orangain/opencv
$ sudo apt-get update
$ sudo apt-get install python3-opencv
```

## How to Build

```
$ wget wget http://http.debian.net/debian/pool/main/o/opencv/opencv_3.0.0+dfsg.orig.tar.xz
$ git clone https://github.com/orangain/opencv
$ cd opencv/
$ git checkout python3
$ debuild -b -rfakeroot -uc -us
```

## How to Release

```
$ dch -U -D trusty  # Then write release notes in your editor
$ git add . ; git commit ; git tag ubuntu/ppaN
$ debuild -S -sa  # GPG key is required
$ dput ppa:orangain/opencv /path/to/opencv_3.0.0+dfsg-1ubuntu1ppaN_source.changes
```
