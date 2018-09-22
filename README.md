# ODK Website

![Platform](https://img.shields.io/badge/platform-Jekyll-blue.svg) [![Ruby version](https://img.shields.io/badge/ruby-2.5.1-blue.svg)](https://www.ruby-lang.org/en/downloads/) [![License](https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/) [![Build status](https://circleci.com/gh/opendatakit/website.svg?style=shield&circle-token=:circle-token)](https://circleci.com/gh/opendatakit/website/) [![Slack status](http://slack.opendatakit.org/badge.svg)](http://slack.opendatakit.org/)

## Table of Contents

* [Developing locally](#developing-locally)
	- [Installing Ruby](#installing-ruby)
		- [GNU/Linux](#gnu/linux)
		- [MacOS](#macos)
		- [Windows](#microsoft-windows)
	- [Installing website](#installing/running-opendatakit/website)
	- [Contributing](#contributing)
	- [Troubleshooting](#troubleshooting)

## Developing locally

### Installing Ruby

OpenDataKit/website is built with [Ruby](https://www.ruby-lang.org/en/downloads/).

However, we suggest that *nix users install and manage Ruby through [`rbenv`](https://github.com/rbenv/rbenv#readme).

A short list of `rbenv`'s advantages can be found [here](https://github.com/rbenv/rbenv/wiki/Why-rbenv%3F). Please consult the `rbenv` [documentation](https://github.com/rbenv/rbenv#basic-github-checkout) or look to Google for the most recent installation instructions for your distribution.

Windows users should use [RubyInstaller](https://rubyinstaller.org/).

#### GNU/Linux

**Known Installation Guides**
DigitalOcean provides guides for installing Ruby with rbenv on [Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-18-04), [Debian 8](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-debian-8), and [CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-centos-7).

**Installation Script**
Alternatively, `rbenv` offers the [`rbenv-installer`](https://github.com/rbenv/rbenv-installer#rbenv-installer), a script which idempotently installs or updates `rbenv` on your system.

**Installing Ruby**
To install Ruby once `rbenv` has been installed:
`$ rbenv install 2.5.1`

Set your default Ruby version. If you'd like to maintain different versions of Ruby for different projects, use [`rbenv-local`](https://github.com/rbenv/rbenv#rbenv-local).
`$ rbenv global 2.5.1`

Verify that Ruby was properly installed by checking its version number:
`$ ruby -v`

#### MacOS

Simple installation instructions using Homebrew can be found in the [`rbenv` documentation](https://github.com/rbenv/rbenv#homebrew-on-macos).

**Installing Ruby**
To install Ruby once `rbenv` has been installed:
`$ rbenv install 2.5.1`

Set your default Ruby version. If you'd like to maintain different versions of Ruby for different projects, use [`rbenv-local`](https://github.com/rbenv/rbenv#rbenv-local).
`$ rbenv global 2.5.1`

Verify that Ruby was properly installed by checking its version number:
`$ ruby -v`

#### Microsoft Windows

Windows users should use [RubyInstaller](https://rubyinstaller.org/).

### Installing/Running OpenDataKit/website

1. Ensure Ruby is installed.
`$ ruby -v`

2. Navigate to the directory under which you plan to develop.
`$ cd /MY/DEVELOPMENT/DIRECTORY`

3. Clone this repository.
`$ git clone https://github.com/opendatakit/website.git`

4. Navigate into the newly cloned project directory `website`.
`$ cd website`

5. Install `bundler`.
`$ gem install bundler`

6. From Install this project.
`$ bundle install`

6. Launch the server.
`$ bundle exec jekyll serve`

The local site will update as changes are made.

## Contributing

One quick way to contribute is to review the [website](https://opendatakit.org) and [file issues](https://github.com/opendatakit/website/issues) documenting the problems you see. If you would like to help fix those issues, see [the contribution guide](CONTRIBUTING.md).

## Troubleshooting

### Permissions

If you encounter the following error:
`You don't have write permissions for the /var/lib/gems/2.3.0 directory.`
then please review the installation instructions to make use of `rbenv`.

Only root has write permissions for `/var/lib`; using `sudo` for subsequent `gem install` comands won't work, and changing permissions for that directory using `chmod` is considered dangerous. This issue is avoided when using `rbenv`.

### Nokogiri

[Nokogiri (鋸)](http://www.nokogiri.org/) is a Rubygem providing HTML, XML, SAX, and Reader parsers with XPath and CSS selector support.

The installation command `bundle install` tries to install `nokogiri`.

If you face following error:
	`Gem::Ext::BuildError: ERROR: Failed to build gem native extension.`

You can fix it as follows:

For Ubuntu/Debian OS:
Run the command `sudo apt-get install build-essential patch ruby-dev zlib1g-dev liblzma-dev` and try again.

If you are using any other OS, you can follow the instructions mentioned here:
http://www.nokogiri.org/tutorials/installing_nokogiri.html
