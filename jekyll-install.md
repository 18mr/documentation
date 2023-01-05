# Install Jekyll

This tutorial assumes that the user is
familiar with a terminal command line interface.
These instructions were performed on both 
Intel and M1 Macs.

### Clone the desired microsite


### Install Ruby
1. Install [rvm](https://rvm.io/rvm/install)
   - The commands (if you don't want to read through):
       - For both types of Macs run to install rvm: `curl -sSL https://get.rvm.io | bash -s stable`
       - For M1 Mac:
           - `echo "source $HOME/.rvm/scripts/rvm" >> ~/.zhrc`
           - Source the .zshrc `. ~/.zshrc`
       - For Intel Mac:
         - `echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile`
         - Source the .bash_profile `. ~/.bash_profile`
    - Verify that it works with `rvm -v`
2. Install a ruby version: 2.6.x < version < 3.x.x
    - `rvm install 2.7.5` works well for the site
    - Explicitly use version: `rvm use 2.7.5`
    - For Intel Macs, this should be enough to install the gems.

## Install gems
1. Install bundler: `gem install bundler:2.0.2`
2. Update bundler: `bundle update --bundler`
3. Install gems: `bundle install`
     - For Mac M1:
         - If there is an error with `nokogiri`, run 
           `bundle config build.nokogiri --use-system-libraries`
         - Run `bundle install` again.
         - If there is an error with `ffi`, run `bundle update ffi`
         - Run `bundle install` again.
4. Check to see if Jekyll is installed by running: `jekyll`. 
    - If Jekyll is not installed, run `gem install jekyll`

## Run the site locally
1. There are two commands that run the site locally
  - `jekyll serve --watch`
  - If the above command does not work, try: `bundle exec jekyll serve --watch`
2. Verify that the site is running by going to http://localhost:4000
    
    