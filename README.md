Heroku buildpack: lighttpd + php (Laravel 4 Flavour)
==========================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for [lighttpd](http://www.lighttpd.net/).

The buildpack will build lighttpd from the source code. The binaries will be
cached to speed up upcoming builds.

Usage
-----

Example usage:

    $ ls
    public_html/

    $ heroku create --stack cedar --buildpack git://github.com/peach-schnapps/heroku-buildpack-lighttpd.git

    $ git push heroku master
    ...
    -----> Fetching custom git buildpack... done
    -----> Installing PHP version $PHP_VERSION
    -----> lighttpd app detected
    -----> Bundling lighttpd version 1.4.32
           Downloading source... done
           Building... done
           Caching binaries... done
           Copying cached binaries... done

You can also add it to upcoming builds of an existing application:

    $ heroku config:add BUILDPACK_URL=git://github.com/peach-schnapps/heroku-buildpack-lighttpd.git

The buildpack will detect your app as lighttpd if it has the directory
`public` in the root (as laravel does)

You can provide a `lighttpd.conf` file to alter the behavior of lighttpd.

License
-------

The buildpack is made available under The MIT License.
