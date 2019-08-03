# Shlink coding standard

This repository provides a [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) ruleset with the rules used by shlink PHP projects.

## Usage

First, install this package using composer:

    composer install shlinkio/php-coding-standard

Then, update your `phpcs.xml` file, adding a rule with the reference to **Shlinkio**.

```xml
<?xml version="1.0"?>
<ruleset name="Coding standard">
    <description>Coding standard</description>

    <!-- display progress -->
    <arg value="p" />
    <arg name="colors" />

    <!-- inherit rules from: -->
    <rule ref="Shlinkio" />

    <!-- [...] -->
</ruleset>
```

## Rules

This ruleset extends [PSR-2](https://www.php-fig.org/psr/psr-2/) rules, and includes:

* Do not allow array long syntax [`array(...)`].
* Make sure string concatenation operator is surrounded by spaces.
* Do not allow superfluous whitespaces.
* Require `declare(strict_types=1);` at the beginning of every PHP file.
* Do not allow unused use statements.
* Require alphabetically ordered use statements.
* Require strict comparisons (`===` and `!==` instead of `==` and `!=`).
* Require trailing comma on every element of multi-line arrays.
* Require no spaces between return type hint colon and function closing brace [`function (...): string`].
* Enforce all global namespace classes, functions and constants to be explicitly imported.
* Require comments with single line written as one-liners [`/* @var SomeType **/`].
* Require import blocks (`use`, `use const` and `use function`) to be separated by an empty line.
* Make all class constants to have a visibility modifier (`public`, `protected` or `private`).
* Require function arguments with a default `null` value to be defined as nullable (`?string $foo = 'foo'`).
