# Herald Prompts

Auto-generated reference for the herald MCP prompt surface. Run
`ddev craft herald/docs/prompts` to refresh.

One prompt is registered per bundled skill that herald maps to a
prompt name, so the total moves with the skills corpus version
below.

- **Total prompts:** 13
- **Skills corpus:** `v1.22.0` (michtio/craftcms-claude-skills)
- **Generated:** 2026-11-02T18:38:16+00:00

## `craftcms_cloud`

Craft Cloud, Pixel & Tonic's serverless hosting for Craft CMS: craft-cloud.yaml configuration, the Build → Migrate → Release deploy pipeline, edge image transforms and static caching, the ephemeral Cloud filesystem, plugin Cloud-compatibility requirements, and self-hosted → Cloud migration.

## `craftcms_content_modeling`

Content modeling principles for Craft CMS: sections, entry types, fields, matrices, relations, propagation, and how to design schemas that scale across editors and sites.

## `craftcms_cp_javascript`

The only written documentation for Garnish, Craft CMS's built-in Control Panel JavaScript toolkit: the class system, UI widgets (Modal, HUD, DisclosureMenu, Select), drag interactions, form components, and accessibility helpers.

## `craftcms_pest`

Testing Craft CMS plugins and modules with Pest and the markhuot/craft-pest-core harness: test isolation and database safety (rollback is opt-in, phpunit.xml.dist env pins, fail-closed database guards), installing the plugin under test, factories, HTTP, queue, and database assertions, and CI test jobs.

## `craftcms_php_standards`

PHP coding standards for Craft CMS plugin and module development: PHPDocs, section headers, naming conventions, class organization, and ECS/PHPStan configuration.

## `craftcms_plugin_release`

Releasing Craft CMS plugins: the composer.json version key, tagging, Packagist propagation and the silent "Skipped tag" failure, GitHub release objects, branch promotion, shared-library release ordering, history rewrites, and path repositories.

## `craftcms_plugins`

Plugin integration guides for Craft CMS, distilled from full plugin documentation: configuration, Twig API, PHP API, migrations, deployment, and pitfalls for Formie, SEOmatic, Blitz, Feed Me, Imager-X, ImageOptimize, CKEditor, Sprig, Retour, Navigation, Hyper, Vite, Warp, and more. Use whenever a task names one of these plugins.

## `craftcms_setup`

Standard project setup playbook for new Craft CMS sites: DDEV bootstrap, plugin selection, project config conventions, and getting from zero to a working dev environment.

## `craftcms_templates`

Complete Craft CMS front-end framework and methodology: atomic design and template architecture, components, layout chains, content builders, image presets, Tailwind conventions, JavaScript boundaries, the Vite buildchain, front-end auth, and headless setup. Plugin-specific guidance lives in craftcms_plugins.

## `craftcms_twig_standards`

Twig coding standards for Craft CMS templates: template structure, naming, accessibility, performance, and how to keep templates clean as a project grows.

## `craftcms_extending`

Reverse-engineered Craft CMS internals: 15-step element save lifecycle, four-layer authorization model, dual-layer session architecture, plus the full plugin/module extension surface (services, controllers, queue jobs, project config, GraphQL). Far beyond official docs.

## `craftcms_ddev`

DDEV usage and troubleshooting for Craft CMS development: local environment setup, container management, common commands, and integration with composer/npm/craft tooling.

## `craftcms_servd`

Servd managed hosting for Craft CMS: git push-to-deploy with servd.yaml, the asset-storage plugin and CDN, static caching alongside Blitz, the local → staging → production workflow with uni-directional project config sync, and how Servd differs from Craft Cloud.

