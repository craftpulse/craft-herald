# Installation & Setup

Herald is installed from its GitHub repository with Composer. It is not listed on the Craft Plugin Store.

## Requirements

Herald requires Craft CMS 5.10.8 or greater and PHP 8.2 or greater.

## Composer

1. Add the repository and the package to your project's `composer.json`, merging them into any existing `repositories` and `require` keys:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/craftpulse/craft-herald"
        }
    ],
    "require": {
        "craftpulse/craft-herald": "^5.0@alpha"
    }
}
```

The repository is public, so no SSH key or access token is needed.

2. Tell Composer to fetch the plugin, then Craft to install it:

```shell
composer update craftpulse/craft-herald
php craft plugin/install herald
```

The `@alpha` flag lets Composer install the current pre-release, starting with `5.0.0-alpha.1`. Drop it once a stable 5.0.0 is tagged.

## DDEV

The same from the command line, through DDEV from the project root. The first two commands write the `repositories` and `require` entries above for you:

```shell
ddev composer config repositories.herald vcs https://github.com/craftpulse/craft-herald
ddev composer require "craftpulse/craft-herald:^5.0@alpha"
ddev craft plugin/install herald
```

## Next steps

Herald serves nothing until an MCP client is pointed at it. Run `php craft herald/install` for a copy-paste snippet per client, then see [Connecting a client](CONNECTING.md).

## Licensing

You can try Herald in a development environment for as long as you like. Once your site goes live, you are required to purchase a license for the plugin.

For more information, see [Craft's Commercial Plugin Licensing](https://craftcms.com/docs/5.x/extend/plugin-store.html#commercial-plugins).
