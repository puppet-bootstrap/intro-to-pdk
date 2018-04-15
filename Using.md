<!SLIDE >
# Creating a Module - The Old Way

    @@@ Console nochrome
    $ puppet module generate author-modulename --skip-interview
    $ cd modulename

*...Lots of editing...*

    @@@ Console nochrome
    $ puppet module build

*...Upload to Forge...*

<!SLIDE >
# What's Wrong With the Old Way?

* Module skeleton quality varied wildly.
* Often easier to create everything from scratch.
* The skeleton was only used as an initial template.
* `puppet module generate` [was deprecated in Puppet 5.4.0](https://puppet.com/docs/puppet/5.4/release_notes.html#deprecations).

<!SLIDE >
# Creating a Module - The New Way

    @@@ Console nochrome
    $ pdk new module author-modulename
    $ cd modulename
    $ pdk new class modulename

*...Lots of editing...*

    @@@ Console nochrome
    $ pdk validate
    $ pdk test unit
    $ pdk build

*...Upload to Forge...*

<!SLIDE >
# Why is this better?

* Generated code follows best practices.
* `pdk new class classname` creates ***manifests/classname.pp*** *and* ***spec/classes/classname_spec.rb***.
    * Testing out of the box!
* The default templates (https://github.com/puppetlabs/pdk-templates) include lots of goodies:
    * CI configurations for Travis CI, GitLab CI/CD, and AppVeyor
    * *operatingsystem_support* and *requirements* in ***metadata.json***
    * Git configuration (***.gitignore***, ***.gitattributes***)
    * [Puppet Strings](https://github.com/puppetlabs/puppet-strings) in generated code
* Updates to the templates can be applied to (some files in) the module.
* Interaction with Ruby tooling (`bundle`, `rake`) is not required.
* Did I mention that `puppet module generate` [was deprecated in Puppet 5.4.0](https://puppet.com/docs/puppet/5.4/release_notes.html#deprecations)?

<!SLIDE >
# Using PDK

## Create a new module

    @@@ Console nochrome
    $ pdk new module mynewmodule

(Or you can skip the interview...)

    @@@ Console nochrome
    $ pdk new module mynewmodule --skip-interview

## Convert an existing module to PDK format

    @@@ Console nochrome
    $ pdk convert

*(Note that this does not add tests for existing classes, defined types, etc.)*

## Update from the templates in an existing PDK-format module

    @@@ Console nochrome
    $ pdk update

<!SLIDE >
# Using PDK

## Create a new class

    @@@ Console nochrome
    $ pdk new class classname

## Create a new defined type

    @@@ Console nochrome
    $ pdk new defined_type typename

## Create a new task

    @@@ Console nochrome
    $ pdk new task taskname
