# docker-ruby-alpine-therubyracer [![Docker Build Status](https://img.shields.io/docker/build/joenyland/ruby-alpine-therubyracer.svg)][docker-hub-image]

This image is based on the [official Ruby image][ruby-image] for Alpine Linux. It contains
[`therubyracer`][therubyracer] gem and the [`libv8`][libv8] gem installed with a V8 engine that's built against the
[`musl` C library][musl] that Alpine Linux uses.

If you need a JS runtime in your Ruby app, one can, of course, just install NodeJS in Alpine Linux and [ExecJS will
just use that][execjs]. If you'd prefer not to use NodeJS, then you can use this image to base your app on.

## Example

```
docker run -it --rm joenyland/ruby-alpine-therubyracer
irb(main):001:0> require 'v8'
=> true
irb(main):002:0> V8::Context.new.eval 5 * 9
=> 45
```

## Contributing

* Any issues, please file a new issue [here][issues].
* Happy to accept pull requests: please raise one [here][prs].

## To Do
 * v8/libv8 versions
 * Why did I create this? Original issue, etc.

[ruby-image]: https://hub.docker.com/_/ruby/
[therubyracer]: https://github.com/cowboyd/therubyracer
[musl]: https://www.musl-libc.org
[issues]: https://github.com/JoeNyland/docker-ruby-alpine-therubyracer/issues
[prs]: https://github.com/JoeNyland/docker-ruby-alpine-therubyracer/pulls
[execjs]: https://github.com/rails/execjs#readme
[libv8]: https://github.com/cowboyd/libv8
[docker-hub-image]: https://hub.docker.com/r/joenyland/ruby-alpine-therubyracer/
