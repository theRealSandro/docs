<!--

********************************************************************************

WARNING:

    DO NOT EDIT "memcached/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "memcached/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links

-	[`1.4.35`, `1.4`, `1`, `latest` (*debian/Dockerfile*)](https://github.com/docker-library/memcached/blob/0c32d28898ba19637ab990b3c092b9e178dfade0/debian/Dockerfile)
-	[`1.4.35-alpine`, `1.4-alpine`, `1-alpine`, `alpine` (*alpine/Dockerfile*)](https://github.com/docker-library/memcached/blob/0c32d28898ba19637ab990b3c092b9e178dfade0/alpine/Dockerfile)

For more information about this image and its history, please see [the relevant manifest file (`library/memcached`)](https://github.com/docker-library/official-images/blob/master/library/memcached). This image is updated via [pull requests to the `docker-library/official-images` GitHub repo](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Fmemcached).

For detailed information about the virtual/transfer sizes and individual layers of each of the above supported tags, please see [the `repos/memcached/tag-details.md` file](https://github.com/docker-library/repo-info/blob/master/repos/memcached/tag-details.md) in [the `docker-library/repo-info` GitHub repo](https://github.com/docker-library/repo-info).

# What is Memcached?

Memcached is a general-purpose distributed memory caching system. It is often used to speed up dynamic database-driven websites by caching data and objects in RAM to reduce the number of times an external data source (such as a database or API) must be read.

Memcached's APIs provide a very large hash table distributed across multiple machines. When the table is full, subsequent inserts cause older data to be purged in least recently used order. Applications using Memcached typically layer requests and additions into RAM before falling back on a slower backing store, such as a database.

> [wikipedia.org/wiki/Memcached](https://en.wikipedia.org/wiki/Memcached)

# How to use this image

```console
$ docker run --name my-memcache -d memcached
```

Start your memcached container with the above command and then you can connect you app to it with standard linking:

```console
$ docker run --link my-memcache:memcache -d my-app-image
```

The memcached server information would then be available through the ENV variables generated by the link as well as through DNS as `memcache` from `/etc/hosts`.

How to set the memory usage for memcached

```console
$ docker run --name my-memcache -d memcached memcached -m 64
```

This would set the memcache server to use 64 megabytes for storage.

For infomation on configuring your memcached server, see the extensive [wiki](https://github.com/memcached/memcached/wiki).

# Image Variants

The `memcached` images come in many flavors, each designed for a specific use case.

## `memcached:<version>`

This is the defacto image. If you are unsure about what your needs are, you probably want to use this one. It is designed to be used both as a throw away container (mount your source code and start the container to start your app), as well as the base to build other images off of.

## `memcached:alpine`

This image is based on the popular [Alpine Linux project](http://alpinelinux.org), available in [the `alpine` official image](https://hub.docker.com/_/alpine). Alpine Linux is much smaller than most distribution base images (~5MB), and thus leads to much slimmer images in general.

This variant is highly recommended when final image size being as small as possible is desired. The main caveat to note is that it does use [musl libc](http://www.musl-libc.org) instead of [glibc and friends](http://www.etalabs.net/compare_libcs.html), so certain software might run into issues depending on the depth of their libc requirements. However, most software doesn't have an issue with this, so this variant is usually a very safe choice. See [this Hacker News comment thread](https://news.ycombinator.com/item?id=10782897) for more discussion of the issues that might arise and some pro/con comparisons of using Alpine-based images.

To minimize image size, it's uncommon for additional related tools (such as `git` or `bash`) to be included in Alpine-based images. Using this image as a base, add the things you need in your own Dockerfile (see the [`alpine` image description](https://hub.docker.com/_/alpine/) for examples of how to install packages if you are unfamiliar).

# License

View [license information](https://github.com/memcached/memcached/blob/master/LICENSE) for the software contained in this image.

# Supported Docker versions

This image is officially supported on Docker version 17.03.0-ce.

Support for older versions (down to 1.6) is provided on a best-effort basis.

Please see [the Docker installation documentation](https://docs.docker.com/installation/) for details on how to upgrade your Docker daemon.

# User Feedback

## Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/docker-library/memcached/issues). If the issue is related to a CVE, please check for [a `cve-tracker` issue on the `official-images` repository first](https://github.com/docker-library/official-images/issues?q=label%3Acve-tracker).

You can also reach many of the official image maintainers via the `#docker-library` IRC channel on [Freenode](https://freenode.net).

## Contributing

You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/docker-library/memcached/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.

## Documentation

Documentation for this image is stored in the [`memcached/` directory](https://github.com/docker-library/docs/tree/master/memcached) of the [`docker-library/docs` GitHub repo](https://github.com/docker-library/docs). Be sure to familiarize yourself with the [repository's `README.md` file](https://github.com/docker-library/docs/blob/master/README.md) before attempting a pull request.
