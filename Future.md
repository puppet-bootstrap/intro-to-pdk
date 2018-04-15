<!SLIDE >
# Future of PDK

PDK has experimental support for creating a new provider with `pdk new provider`.
See https://github.com/puppetlabs/puppet-resource_api#getting-started for more information.

Other interesting features that may be coming soon:

* More module features
  * `pdk new function` [PDK-700](https://tickets.puppetlabs.com/browse/PDK-700)
  * `pdk new fact` [PDK-683](https://tickets.puppetlabs.com/browse/PDK-683)
* Multi-Puppet Support [PDK-414](https://tickets.puppetlabs.com/browse/PDK-414)
    * Support for additional platforms [PDK-399](https://tickets.puppetlabs.com/browse/PDK-399)
    * Testing on multiple Puppet and Ruby versions
      [PDK-785](https://tickets.puppetlabs.com/browse/PDK-785),
      [PDK-840](https://tickets.puppetlabs.com/browse/PDK-840), etc.
* Data in modules by default [PDK-908](https://tickets.puppetlabs.com/browse/PDK-908)
* CLI ability to update ***metadata.json*** [PDK-878](https://tickets.puppetlabs.com/browse/PDK-873)
* Improved CI/CD support [PDK-477](https://tickets.puppetlabs.com/browse/PDK-477)
* Control repo support [PDK-564](https://tickets.puppetlabs.com/browse/PDK-564),
  [puppetlabs/pdk#333](https://github.com/puppetlabs/pdk/issues/333)
* [Bundled git support](https://github.com/puppetlabs/pdk/pull/331)
