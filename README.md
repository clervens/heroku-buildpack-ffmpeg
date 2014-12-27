Heroku buildpack: FFMpeg
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [ffmpeg](http://www.ffmpeg.org/) in your project.  
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.  

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/shunjikonishi/heroku-buildpack-ffmpeg
    https://github.com/heroku/heroku-buildpack-nodejs

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify installing ffmpeg by following command. (Must be 2.5.1 Dec 18 2014)

    $ heroku run ffmpeg --version

Hacking
-------
If you want to use your own ffmpeg binary, fork and rewrite following line.

https://github.com/clervens/heroku-buildpack-ffmpeg/blob/master/bin/compile#L10
