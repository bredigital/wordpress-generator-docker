# BRE Digital WordPress Generator
**Please be aware that this development is in beta, and is not intended for use within a production environment.**

WordPress Generator is an application designed for spinning up temporary WordPress installations for testing and development purposes. Once finished, the site can be exported or deleted. All through the Power of [WP-CLI][wpcli]!

*This readme for Docker is in progress. [Please see the main repository][repo] for more project and usage details.*

## Persistence
Bind `/var/www/html/sites` to a volume. This is the only directory required for persistence (database also needs to be persisted), and will survive container destruction.

Further bindings can be used. They are (paths start with `/var/www/html/`):
- `assets/wordpress/(themes\plugins\mu-plugins)` Files and folders in here are deployed to each new container.
- `assets/exports` for persistent export storage.

[repo]:  https://github.com/bredigital/wordpress-generator
[wpcli]: https://wp-cli.org/
