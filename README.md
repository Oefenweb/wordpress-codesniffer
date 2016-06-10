# Oefenweb Code Sniffer for Wordpress

This code works with [phpcs](https://github.com/squizlabs/PHP_CodeSniffer) and checks code against the coding standards used at Oefenweb.

## Installation

It's generally recommended to install these code sniffs with `composer`:

```sh
composer global require --dev 'wp-coding-standards/wpcs=~0.9';
```

Modify `~/.composer/composer.json`.

```json
"require-dev": {
	"oefenweb/wordpress-codesniffer": "dev-master"
},
"repositories": [
	{
		"type": "vcs",
		"url": "https://github.com/Oefenweb/wordpress-codesniffer"
	}
]
```

```sh
composer global update oefenweb/wordpress-codesniffer;
~/.composer/vendor/bin/phpcs --config-set \
	installed_paths "${HOME}/.composer/vendor/wp-coding-standards/wpcs,${HOME}/.composer/vendor/oefenweb/wordpress-codesniffer";
```

This lets `phpcs` know where to find your new sniffs. Ensure that you do not overwrite any existing `installed_paths` value.

## Usage

When these sniffs are installed with `composer`, ensure that you have configured the CodeSniffer `installed_paths` setting.

Once `installed_paths` is configured, you can run phpcs using:

```sh
~/.composer/vendor/bin/phpcs . --standard=WordpressOefenweb --extensions=php;
```
