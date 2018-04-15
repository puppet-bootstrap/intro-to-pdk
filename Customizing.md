<!SLIDE >
# PDK Templates

The default PDK templates can be found here:

https://github.com/puppetlabs/pdk-templates

Files in the ***moduleroot\_init*** directory are created only if they don't exist.

Files in the ***moduleroot*** directory will replace any existing file when you run
`pdk update` or `pdk convert`.

Files in the ***object\_templates*** directory are used by the various `pdk new`
commands.

The default settings for the template output can be found in the file
***[config_defaults.yml](https://github.com/puppetlabs/pdk-templates/blob/master/config_defaults.yml)***.

<!SLIDE >
# Customizing Template Output

Settings in the file ***.sync.yml*** in the root of your module can be used to
customize the output of the templates.

***.sync.yml*** contains a hash.  The keys of the hash are the names of the generated
files.  The exact values can be found by looking at the
[PDK templates ***README.md***](https://github.com/puppetlabs/pdk-templates/blob/master/README.md),
[***config_defaults.yml*** in the templates](https://github.com/puppetlabs/pdk-templates/blob/master/config_defaults.yml),
and the code of the templates.

After updating ***.sync.yml***, run `pdk update` to regenerate files from the templates.

<!SLIDE >
# Example ***.sync.yml***

    @@@ yaml
    ---
    Gemfile:
      optional:
        ':acceptance':
          - gem: beaker
          - gem: beaker-rspec
          - gem: beaker-puppet_install_helper
          - gem: beaker-module_install_helper
          - gem: vagrant-wrapper
    .gitignore:
      paths:
        - /update_report.txt
    spec/spec_helper.rb:
      spec_overrides: |-
        # Add coverage report.
        RSpec.configure do |c|
          c.after(:suite) do
            RSpec::Puppet::Coverage.report!
          end
        end

