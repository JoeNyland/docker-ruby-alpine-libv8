# docker-ruby-alpine-libv8 [![Docker Build Status](https://img.shields.io/docker/build/joenyland/ruby-alpine-libv8.svg)][docker-hub-image]

This image is based on the [official Ruby image][ruby-image] for Alpine Linux. It contains
the [`libv8`][libv8] gem installed with a V8 engine that's built against the
[`musl` C library][musl] that Alpine Linux uses.

One can, of course, just install NodeJS in Alpine Linux and [ExecJS will just use that][execjs-readme]. If you'd prefer
not to use NodeJS, then you can use this image to base your app on.

## Example

Here's what happens with the normal Alpine based Ruby image: 

```
docker run -it --rm ruby:alpine sh
apk add --update --virtual build-deps build-base
gem install therubyracer
irb(main):001:0> require 'v8'
LoadError: Error relocating /usr/local/bundle/gems/therubyracer-0.12.3/lib/v8/init.so: __vfprintf_chk: symbol not found - /usr/local/bundle/gems/therubyracer-0.12.3/lib/v8/init.so
```

And here's it working with this image:

```
docker run -it --rm joenyland/ruby-alpine-libv8
irb(main):001:0> require 'v8'
=> true
irb(main):002:0> V8::Context.new.eval 5 * 9
=> 45
```

## Contributing

* Any issues, please file a new issue [here][issues].
* Happy to accept pull requests: please raise one [here][prs].

[ruby-image]: https://hub.docker.com/_/ruby/
[musl]: https://www.musl-libc.org
[issues]: https://github.com/JoeNyland/docker-ruby-alpine-libv8/issues
[prs]: https://github.com/JoeNyland/docker-ruby-alpine-libv8/pulls
[execjs]: https://github.com/rails/execjs
[execjs-readme]: https://github.com/rails/execjs#readme
[libv8]: https://github.com/cowboyd/libv8
[docker-hub-image]: https://hub.docker.com/r/joenyland/ruby-alpine-libv8/
