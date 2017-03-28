# santosfamilyfoundation.github.io

This is the public site for the Santos Family Foundation SCOPE team at Olin College.

## How To

This site is built using jekyll. Jekyll is a site builder for static sites. It is used to insert portions of html into a template, and render Markdown into HTML.

### Install

Ensure that ruby with a version >= 2.0 is installed.

#### Ruby

The first step is to install Ruby.

##### Ubuntu

On Ubuntu, run this:

```
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
```

Then run:

```
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

rbenv install 2.3.1
rbenv global 2.3.1
ruby -v
```

#### Jekyll and Bundler

Next, install Jekyll and Bundler.

##### Ubuntu

Run:

```
gem install jekyll bundler
```

### Running

From command line, run:

```
bundler exec jekyll server
```

### Add Pages

To add a page, you can create a Markdown (.md) file in the top level directory. Check out [about.md](about.md) for an example of how this works.
