Layout Wildcard
===============

This module allows you to use the same layout on multiple paths. It adds settings to the Layout configuration page where you can specify additional paths on which the layout may be applied (depending on user access and relative layout priority).

Layout Wildcard adds a new "Alternative paths" setting to each layout configuration, which allows specifying a list of multiple additional paths to be handled by the layout.

In addition it implements "ancestor matching," which allows you to stipulate that a layout could be used on all paths of the form `somepath/%` even if there are only specific paths like `somepath/1` and `somepath/2` (but not `somepath/%`) in the menu router table.

Installation
------------

- Install and enable this module using [the official Backdrop CMS instructions](https://backdropcms.org/guide/modules).

- Ancestor matching will take effect as soon as the module is enabled.

- Add any desired additional paths to the "Alternative paths" setting on each layout's configuration page.

Documentation
-------------

Additional documentation is located in [the Wiki](https://github.com/backdrop-contrib/layout_wildcard/wiki/Documentation).

Issues
------

Bugs and feature requests should be reported in [the Issue Queue](https://github.com/backdrop-contrib/layout_wildcard/issues).

See the issue queue for the roadmap of future plans, including support for aliases in addition to normal paths.

Current Maintainers
-------------------

* [Robert J. Lang](http://github.com/bugfolder)

Credits
-------

- Originally written for Backdrop by [Gor Martsen](https://github.com/Gormartsen).

License
-------

This project is GPL v3 software.
See the LICENSE.txt file in this directory for complete text.

