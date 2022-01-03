vips-buildpack
=========================

This project is a Scalingo [buildpack](http://doc.scalingo.com/buildpacks) to
use latest version of [libvips](www.libvips.org) (8.12.1)
alongside your app.

It doesn't do anything else, you have to use it alongside another buildpack thanks to the [multi-buildpack](https://github.com/Scalingo/multi-buildpack).

Usage
-----

## Setup the multi-buildpack

To use this buildpack, you should prepare `.buildpacks` file that contains this buildpack url and your real buildpack url.

```
$ cat .buildpacks
https://github.com/Scalingo/graphicsmagick-buildpack.git
https://github.com/Scalingo/ruby-buildpack.git
```

The first buildpack will install libvips utilities in `/app/bin`, the
second will handle the deployment of your ruby application. For any other
technology, go to
[http://doc.scalingo.com/buildpacks/](http://doc.scalingo.com/buildpacks/)

## Setup your application configuration

```
$ scalingo env-set BUILDPACK_URL=https://github.com/Scalingo/multi-buildpack.git
$ git push scalingo master
...
```
