# SilverStripe Global Error Page Module

## Documentation

This module is used to add Global error pages to a site or a collection sites.
You can use it to specify a path of where to find some standard error pages.
These pages can be plain html which will output the raw html of the file or it
can be a php file which it will just output the response from a php file.

## Requirements

* SilverStripe 3.2

## Composer Installation

    composer require marketo/silverstripe-universalerrorpage

## Maintainer Contacts

- Nathan J. Brauer (nathan@marketo.com)
- Kirk Mato (kmayo [at] solnet.co.nz)

## Config

The module can be modified via a YAML file to specify a path or a particular
file for a certain error code.
To define a path specify this in a YAML config file under `GlobalErrorPage`
with the name `GlobalErrorPagePath`
If no path is defined it defaults to `/var/www/error_pages/`
You can also specify a page for a particular error code under `GlobalErrorPage`.

#### Sample YAML config

```
GlobalErrorPage:
  ConvertOnDevBuild: true
  GlobalErrorPagePath: '/etc/apache2/error/'
  404: '/etc/apache2/error/error.php'
```

Any existing SilverStripe error pages will need to be removed as well as the
static html files which are created in assets.

## TODO

- [ ] Add Tests
- [ ] Fix Extension point and test it
- [ ] Add dev task to remove SilverStripe Error pages and static error pages
- [ ] Find way to prevent /dev/build from generating static pages