# Coding Standards

Basic php linting rulesets

## Installation

Add composer repository to your `composer.json`:

```json
    ...
    "repositories": [
        {
            "type": "composer",
            "url": "http://composer.lloydculpepper.uk"
        }
    ]
    ...
```

You can then install the package via composer:

```bash
$ composer require opvl/php-rulesets --dev
```


## Standard composer scripts

Below are the script we recommend you add to your `composer.json` to simplify working with these tools.

```
"scripts": {
  "php-lint": "vendor/bin/parallel-lint --exclude vendor --exclude node_modules --exclude sdk/vendor .",
  "phpcs": "vendor/bin/phpcs YOUR_DIRECTORIES --standard=./vendor/opvl/php-rulsets/phpcs.xml",
  "doc-check": "vendor/bin/php-doc-check YOUR_DIRECTORIES",
  "lint": [
    "@composer php-lint",
    "@composer phpcs",
    "@composer doc-check",
  ],
  "cbf": "vendor/bin/phpcbf YOUR_DIRECTORIES --standard=./vendor/opvl/php-rulsets/phpcs.xml",
}
```
