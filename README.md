# BM WordPress Development Tools

These are a set of development tools that we use for WordPress development in our plugins and themes.

The tools consists of:

- PHPStan and WordPress rules
- PHPCS ruleset
- PHPCS Fixer

## Installation

To use this in your project, require this package as a composer dev-dependency:

```bash
composer require bernskioldmedia/bm-wp-devtools --dev
```

Add the following scripts to your composer.json:

```json
{
  "scripts": {
	"lint": "php-cs-fixer fix -v",
	"test:cs": "phpcs-wp",
	"test:types": "phpstan analyse --ansi --memory-limit=-1",
	"test:lint": "php-cs-fixer fix -v --dry-run",
	"test": [
	  "@test:lint",
	  "@test:types"
	]
  }
}
```

## Configure PHP Storm

### PHPCS Inspections

1. go to `Project Settings > PHP > Code Sniffer` and set your phpcs executable. You should use installed in bin-dir.
2. go to Project `Settings > Inspections > PHP > PHP Code Sniffer validation` and set Custom coding standard.
3. use path selection ("...") to find the ruleset at `vendor/bernskioldmedia/bm-wp-devtools/phpcs/ruleset.xml`
