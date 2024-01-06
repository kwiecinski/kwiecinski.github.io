# Webpage created using Jekyll and Minimal Mistakes theme

- [Jekyll documentation] https://jekyllrb.com/docs/
- [Minimal Mistakes theme documentation] https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
  
## Setup enviroment for Jekyll on Ubuntu

Install Ruby and other prerequisites:

`sudo apt-get install ruby-full build-essential zlib1g-dev`

Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path:

```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Finally, install Jekyll and Bundler:

`gem install jekyll bundler`

That’s it! You’re ready to start using Jekyll.

## Create Jekyll site

Install the jekyll and bundler gems.

`gem install jekyll bundler`

Create a new Jekyll site at ./myblog.

`jekyll new myblog`

Change into your new directory.

`cd myblog`

Build the site and make it available on a local server.

`bundle exec jekyll serve --livereload`

Browse to [http://localhost:4000](http://localhost:4000)

## Configure minimMinimal Mistakes theme

Add the following to your Gemfile:

`gem "minimal-mistakes-jekyll"`

Fetch and update bundled gems by running the following Bundler command:

`bundle`

Set the theme in your project’s Jekyll _config.yml file:

`theme: minimal-mistakes-jekyll`

To update the theme run bundle update.



