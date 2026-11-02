# Herald

Herald is a [Model Context Protocol](https://modelcontextprotocol.io/) server for Craft CMS that exposes your content model, your content, and a bundled corpus of authored Craft expertise to an MCP client, over a trusted local transport or an authenticated HTTP endpoint.

## Features

- 33 tools in Free covering the content model, content reads, system state, GraphQL, and workflow audits, rising to 42 in Pro with the content-write and user surfaces.
- A bundled corpus of hand-authored Craft expertise, served as MCP prompts, as individually addressable resources, and through keyword search.
- Two transports: a stdio console server for local clients, and a Streamable HTTP endpoint with OAuth 2.1, bearer tokens, and per-request authorization (Pro).
- Tool arguments validated against their declared JSON Schema at the dispatcher, before any tool sees an argument.
- Capability scopes on every HTTP credential, where an absent scope denies rather than allows.
- An allowlist for Craft console commands, layered across project config, per-environment file overrides, and expiring runtime grants.
- Content writes through Craft's element API only, with per-section and per-group permission checks re-run inside every write (Pro).
- One audit row and one structured log line per invocation with secrets redacted, plus native [Audit Kit](https://github.com/craftpulse/craft-audit-kit) events so writes reach a tamper-evident chain.
- Control panel screens for settings, temporary command grants, bearer tokens, OAuth client approval, the invocation log, and client connection details.
- Registration events for third-party tools, prompts, and resources, with a `make herald-tool` generator for scaffolding.

## Requirements

### Craft CMS

Herald requires Craft CMS 5.0.0 or greater.

### PHP

Herald requires PHP 8.2 or greater.

### MCP client

Herald requires a client that speaks the Model Context Protocol. Config writers ship for Claude Desktop, Claude Code, Cursor, Continue.dev, Cline, Zed, and Windsurf. Any other client that accepts the standard `command` plus `args` server shape works, without the one-command config writer.

## Installation

Herald is installed from its GitHub repository with Composer. It is not listed on the Craft Plugin Store.

### Composer

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

### DDEV

The same from the command line, through DDEV from the project root. The first two commands write the `repositories` and `require` entries above for you:

```shell
ddev composer config repositories.herald vcs https://github.com/craftpulse/craft-herald
ddev composer require "craftpulse/craft-herald:^5.0@alpha"
ddev craft plugin/install herald
```

## Next steps

Herald serves nothing until an MCP client is pointed at it. To connect one:

- Run `php craft herald/install` to print a copy-paste config snippet for every supported client.
- Or run `php craft herald/install/auto` from your host to detect installed clients and apply the config for each.
- Ask your client something Craft can answer, such as "list the sections in this project", and confirm it calls the `sections` tool.

Full per-client paths, the HTTP transport, and troubleshooting are in [`docs/CONNECTING.md`](docs/CONNECTING.md).

## Documentation

- [Installation](docs/INSTALL.md)
- [Connecting a client](docs/CONNECTING.md)
- [HTTP transport](docs/HTTP-TRANSPORT.md)
- [Configuration](docs/CONFIGURATION.md)
- [Security model](docs/SECURITY.md)
- [Tool reference](docs/TOOLS.md)
- [Prompt reference](docs/PROMPTS.md)
- [Resource reference](docs/RESOURCES.md)
- [Extending Herald](docs/EXTENDING.md)

## Licensing

You can try Herald in a development environment for as long as you like. Once your site goes live, you are required to purchase a license for the plugin.

For more information, see [Craft's Commercial Plugin Licensing](https://craftcms.com/docs/5.x/extend/plugin-store.html#commercial-plugins).

## Support

- Issues: [github.com/craftpulse/craft-herald/issues](https://github.com/craftpulse/craft-herald/issues)
- Email: [support@craft-pulse.com](mailto:support@craft-pulse.com)

## Credits

- [Model Context Protocol](https://modelcontextprotocol.io/), the specification Herald implements.
- [Craft CMS](https://craftcms.com/), Pixel & Tonic.
- [`craftcms/generator`](https://github.com/craftcms/generator), the make system Herald registers `herald-tool` into.
- [`michtio/craftcms-claude-skills`](https://github.com/michtio/craftcms-claude-skills), the bundled skills corpus Herald serves as prompts and resources.

Brought to you by [CraftPulse](https://craft-pulse.com/).
