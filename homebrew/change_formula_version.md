# Change version

Today I trying to run the executable from a gem and got the following error:

```
This installation of RMagick was configured with ImageMagick 6.8.9 but
ImageMagick 6.9.0-3 is in use. (RuntimeError)
```

Through the Google, I fund how to use different Homebrew formula versions [thoughtbot/til][1]

However this method didn't work, after searching on Google I found a method to install a formula directly on Cellar folder.

```
$ brew versions Imagemagick

Warning: brew-versions is unsupported and will be removed soon.
You should use the homebrew-versions tap instead:
  https://github.com/Homebrew/homebrew-versions

6.9.0-3  git checkout 8b2b988 /usr/local/Library/Formula/imagemagick.rb
6.8.9-8  git checkout 9efbcda /usr/local/Library/Formula/imagemagick.rb
6.8.9-7  git checkout fc0f13b /usr/local/Library/Formula/imagemagick.rb
```

I follow the next steps:

```
$ cd /usr/local/Cellar/
$ git checkout 9efbcda /usr/local/Library/Formula/imagemagick.rb
$ brew unlink imagemagick && brew install imagemagick
$ rails server
```

And voila!

[1]: https://github.com/thoughtbot/til/blob/master/homebrew/using_different_homebrew_formula_versions.md
