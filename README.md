# Shopify Forms Bundle (Embed)

## Installation

**Install With Composer**

```json
{
   "require": {
       "sturple/shopify-boilerplate": "dev-master"
   }
}

```

and then execute

```json
$ composer update
```


## Configuration

**Add to ```app/AppKernel.php``` file**

```php

class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = [
            ...
             new Fgms\BoilerPlateBundle\FgmsBoilerPlateBundle();
        ]
    }
}

```

The following configuration options may/must be set in `config.yml`:

```yaml
fgms_boilerplate:
    api_key:            # API key for Shopify
    secret:             # Secret for Shopify
```

## Shopify App Configuration

The bundle specifies the following routes which must be known to configure as a Shopify App:

- **Install:** `/install`
- **OAuth:** `/auth`
- **Home:** `/`

To setup a Shopify proxy for form submission point the proxy at `/submit`.  The unique code for the form to submit to should be appended to the Shopify proxy link.


## Update boilerplate to your class


* grep -rln 'BoilerPlateBundle' * | xargs -i@ sed -i 's/BoilerPlateBundle/MYCLASSBundle/g' @
* grep -rln 'fgms_boilerplate' * | xargs -i@ sed -i 's/fgms_boilerplate/fgms_ALIAS/g' @
* grep -rln 'shopify_boilerplate_store' * | xargs -i@ sed -i 's/shopify_boilerplate_store/shopify_PREFIX_store/g' @
* mv FgmsBoilerPlateBundle.php FgmsMYCLASSBundle.php
* mv DependencyInjection/FgmsBoilerPlateExtension.php DependencyInjection/FgmsMYCLASSBundle.php

