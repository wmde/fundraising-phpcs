# PHP Code style for the WMDE FUN team

This is [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) rule set based on the
[`wikimedia/mediawiki-tools-codesniffer`](https://github.com/wikimedia/mediawiki-tools-codesniffer)
rules which encode the [conventions for MediaWiki
projects](https://www.mediawiki.org/wiki/Manual:Coding_conventions/PHP).

## Deviations from the Mediawiki conventions

* Dont' enforce docblocks. We try to rely on type information as much as
  possible.
* Allow longer line lengths. Lines longer than 120 chars will generate a
  warning. Ignore line length in `tests/*` directory.
* Allow `assert` statements. We still don't use them for all-purpose
  validation, but for some checks that matter in development but not in
  production, `assert` has a few nanoseconds better performance than
  `if` + `throw`.

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
	
## How to run

The installation automatically installs the `phpcs` (style checker) and
`phpcbf` (style fixer) binaries into `vendor/bin`. When your `.phpcs.xml`
file is in place, run the command

	vendor/bin/phpcs
	

## Versioning
This repository should create a new major release whenever the mediawiki
coding standard has a new major release.


