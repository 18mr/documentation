# Install Jekyll

This tutorial assumes that the user is
familiar with a terminal command line interface.
These instructions were performed on both 
Intel and M1 Macs.

### Install Ruby
1. Install [rvm](https://rvm.io/rvm/install)
2. Install a ruby version: 2.6.x < version < 3.x.x
    - `rvm install 2.7.5` works well for the site
    - For Intel Macs, this should be enough to install the gems.

## Install gems
1. Install bundler: `gem install bundler:2.0.2`
2. Update bundler: `bundle update --bundler`
3. Install gems: `bundle install`
     - For Mac M1:
         - If there is an error with `nokogiri`, run 
           `bundle config build.nokogiri --use-system-libraries`
         - If there is an error with `ffi`, run `bundle update ffi`
         - Following these errors, run `bundle install` again.

## Run the site locally
1. There are two commands that run the site locally
  - `jekyll serve --watch`
  - `bundle exec jekyll serve --watch`
    
    