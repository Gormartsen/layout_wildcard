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

Versions
-------------

Backdrop 1.20, introduced September 15, 2021, incorporates [some changes in Layouts](https://github.com/backdrop/backdrop/pull/3618), including the creation of a new hook, `hook_layout_load_by_router_item_alter()`, which (for the first time) provides a way for contrib modules to cleanly alter which layout is used for a given path. A collateral effect of these changes are some improvements in how layouts for node preview pages are handled.

Since altering which layout is used for a given path is very much Layout Wildcard's _raison d'etre_, this change has big ramifications for the future of LW. It lets us simplify the current code and contemplate adding new capabilities in a straightforward way.

The 1.2.x branch of LW works by essentially fully taking over from Backdrop Core the process of determining which layout gets applied to the currently requested path. This did the trick in the past, and will continue to work even after upgrading Backdrop to version 1.20. However, if you upgrade Backdrop to v. 1.20 but keep LW on version 1.2.2, your site will miss out on the node preview fix in 1.20, and if any other modules make use of the new hook, they will not function properly.

This table summarizes the version compatibility of LW and Backdrop core.

<table>
  <tr>
    <td></td>
    <td><strong>Backdrop 1.19.x</strong></td>
    <td><strong>Backdrop 1.20+</strong></td>
  </tr>
  <tr>
    <td><strong>Layout Wildcard 1.2.2</strong></td>
    <td>Works as currently</td>
    <td>Will still work, but no support for new hook and associated functionality</td>
  </tr>
  <tr>
    <td><strong>Layout Wildcard 2.0+</strong></td>
    <td>Will not work</td>
    <td>Recommended!</td>
  </tr>
</table>

We encourage upgrading LW to version 2.0 at the same time that you upgrade Backdrop to version 1.20. Once LW 2.0 is released, all future development of Layout Wildcard will take places on the 2.0 branch.

Layout Wildcard 2.0, in addition to supporting the new hook, also adds proper support for contexts  in alternative paths and makes ancestor matching optional.

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

This project is GPL v2 software.
See the LICENSE.txt file in this directory for complete text.

