Guard::Zeus
===========

Guard::Zeus automatically starts and stops [Zeus](https://github.com/burke/zeus).

[![Build Status](https://travis-ci.org/guard/guard-zeus.png?branch=master)](https://travis-ci.org/guard/guard-zeus)
[![Code Climate](https://codeclimate.com/github/guard/guard-zeus.png)](https://codeclimate.com/github/guard/guard-zeus)

Install
-------

Please be sure to have [Guard](https://github.com/guard/guard) and [Zeus](https://github.com/burke/zeus) installed before continuing.

Install the gem:

    $ gem install guard-zeus

Add it to your Gemfile (inside development group):

``` ruby
gem 'guard-zeus'
```

Add guard definition to your Guardfile by running this command:

    $ guard init zeus

Usage
-----

Please read [Guard usage doc](https://github.com/guard/guard#readme)

Guardfile
---------

Please read [Guard doc](https://github.com/guard/guard#readme) for more information about the Guardfile DSL.

### Options

Available options:

``` ruby
:rspec => false          # Don't use RSpec
:test_unit => false      # Don't use Test::Unit
:bundler => false        # Don't use "bundle exec"
:cli => '--time'         # Pass options to zeus. `zeus commands` for more zeus options
:run_all => true         # Run all tests when hitting enter in guard
```

Known Issues
------------


### Use with pry

There is a known issue when using guard-zeus with pry, notably the zeus output appear on top of the pry console.

The workaround is to add the `cli` setting in your `Guardfile`, e.g.

```
guard 'zeus', cli: '> /dev/null' do
```

### Lingering zeus process

If you have issues with `zeus` lingering around after exiting `guard`, you can
add the following to the top of your `Guardfile`.

```
at_exit {exec('pkill -f zeus')}
```

Development
-----------

* Source hosted at [GitHub](https://github.com/guard/guard-zeus)
* Report issues/Questions/Feature requests on [GitHub Issues](https://github.com/guard/guard-zeus/issues)

Pull requests are very welcome! Make sure your patches are well tested. Please create a topic branch for every separate change
you make.

Authors
------

Based on the awesome [guard-spin](https://github.com/vizjerai/guard-spin). Original authors include:

* [Jonathan](https://github.com/jonsgreen)
* [Andrew Assarattanakul](https://github.com/vizjerai)

Ported to use zeus by:

* [Rob Sharp](https://github.com/qnm)

Many Thanks To
--------------

* [Jesse Storimer](https://github.com/jstorimer)

Alternatives
------------

* [guard/rspec](https://github.com/guard/guard-rspec) has recently picked up Zeus support. You may wish to see if this fits your needs.
* [aceofsales/guard-zeus-client](https://github.com/aceofsales/guard-zeus-client) is very similar to this version.

