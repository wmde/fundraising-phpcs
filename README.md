# PHP Code style for the WMDE FUN team

This is [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) rule set based on the
[`wikimedia/mediawiki-tools-codesniffer`](https://github.com/wikimedia/mediawiki-tools-codesniffer)
rules which encode the [conventions for MediaWiki
projects](https://www.mediawiki.org/wiki/Manual:Coding_conventions/PHP).

## Deviations from the Mediawiki conventions

* Dont' enforce docblocks. We try to rely on type information as much as
  possible.
* Allow long line lengths. Our test cases are complete sentences and
  therefore exceed the line limit.
* Allow `assert` statements. We still don't use them for all-purpose
  validation, but for some checks that don't affect production they are
  useful.

## How to install

1. Require the library as a composer dependency:

	composer require-dev wmde/fundraising-phpcs


2. Create a .phpcs.xml with the following minimal configuration:

    ```
    <?xml version="1.0"?>
    <ruleset>
    	<rule ref="./vendor/wmde/fundraising-phpcs/WMDE/Fundraising"/>
    	<file>.</file>
    	<arg name="extensions" value="php"/>
    	<arg name="encoding" value="UTF-8"/>
    </ruleset>
    ```
