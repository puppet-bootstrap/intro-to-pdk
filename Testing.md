<!SLIDE >
# Testing

Smoke tests (simple `lint`, `rubocop`, and parser checks) can be run with the
following command:

    @@@ Console nochrome
    $ pdk validate

Unit tests (Ruby scripts that use [rspec-puppet](http://rspec-puppet.com/)
to test the contents of a compiled catalog) can be executed with the
following command:

    @@@ Console nochrome
    $ pdk test unit

The default tests use
[rspec-puppet-facts](https://github.com/mcanevet/rspec-puppet-facts)
to test catalog compilation on each supported OS.

~~~SECTION:handouts~~~

https://puppet.com/docs/pdk/1.x/pdk_testing.html

~~~ENDSECTION~~~

<!SLIDE >
# `pdk bundle`

PDK allows you to run arbitrary `bundle` commands with `pdk bundle`.
For example, to see what `rake` tasks are available, you can run the
following command:

    @@@ Console nochrome
    $ pdk bundle exec rake -- -T

To see all output of the `rake` tasks run by `pdk test unit`, you can
run the following command:

    @@@ Console nochrome
    $ pdk bundle exec rake spec

<!SLIDE >
# Acceptance Tests

Acceptance tests spin up VMs or Docker containers to test the behavior of a
module on a live system.

PDK currently has no direct support for acceptance tests, but if you have an
existing module with working tests, you should be able to make some minor
additions to ***Gemfile*** and run the following:

    @@@ Console nochrome
    $ pdk bundle exec rake beaker

For more information on acceptance tests, see the following:

* [beaker-rspec](https://github.com/puppetlabs/beaker-rspec)
* [beaker](https://github.com/puppetlabs/beaker)
* [Serverspec](http://serverspec.org/)
