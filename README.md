# Oefenweb Code Sniffer for Wordpress

This code works with [phpcs](https://github.com/squizlabs/PHP_CodeSniffer) and checks code against the coding standards used at Oefenweb.

## Installation

It's generally recommended to install these code sniffs with `composer`:

```sh
mkdir WordpressOefenweb && cd $_ && composer require oefenweb/wordpress-codesniffer=dev-master;
```

```sh
vendor/bin/phpcs \
  --config-set installed_paths "${PWD}/vendor/wp-coding-standards/wpcs,${PWD}/vendor/oefenweb/wordpress-codesniffer" \
;
```

This lets `phpcs` know where to find your new sniffs. Ensure that you do not overwrite any existing `installed_paths` value.

## Usage

When these sniffs are installed with `composer`, ensure that you have configured the CodeSniffer `installed_paths` setting.

Once `installed_paths` is configured, you can run phpcs using:

```sh
vendor/bin/phpcs --standard=WordpressOefenweb ~/foo/bar/wp-load.php;
```
