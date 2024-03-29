# Behat Drupal Extension
This package relies on Nuvole's [Behat Drupal Extension](https://github.com/nuvoleweb/drupal-behat) and its feature to
override Drupal Core driver.

Behat Drupal Extension provides the following features:

- Additional step definitions covering layout builder functionality

## Installation and setup

```bash
$ composer require kbrodej/drupal-extension-layout-builder
```

Setup the extension by following the [Quick start](https://github.com/jhedstrom/drupalextension#quick-start) section
available on the original Behat Drupal Extension page, just use `NuvoleWeb\Drupal\DrupalExtension` instead of the native
`Drupal\DrupalExtension` in your `behat.yml` as shown below:

```yaml
default:
  suites:
    default:
      contexts:
        - Drupal\DrupalExtension\Context\DrupalContext
        - Kbrodej\Drupal\DrupalExtension\Context\LayoutBuilderContext
        ...
  extensions:
    Behat\MinkExtension:
      goutte: ~
      ...
    # Use "NuvoleWeb\Drupal\DrupalExtension" instead of "Drupal\DrupalExtension".
    NuvoleWeb\Drupal\DrupalExtension:
      api_driver: "drupal"
      ...
      services: "tests/my_services.yml"
      text:
        node_submit_label: "Save and publish"
```

Set core class in `services.yml`

`test/services.yml:`
```yaml
parameters:
  drupal.driver.cores.8.class: Kbrodej\Drupal\Driver\Cores\Drupal8
```

## Additional resources
* [Nuvole's Behat Drupal Extension](https://github.com/nuvoleweb/drupal-behat)
* [Behat Drupal Extension documentation](https://behat-drupal-extension.readthedocs.org)
* [Behat documentation](http://docs.behat.org)
* [Mink documentation](http://mink.behat.org)
* [Drupal Behat group](http://groups.drupal.org/behat)

## Supporting organizations
* [Inviqa](https://inviqa.com/)
* [Agiledrop](https://www.agiledrop.com/)