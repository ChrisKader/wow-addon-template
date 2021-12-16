# @addon-name@

[Addon Description]

## Development

You must use [*packager*](https://github.com/BigWigsMods/packager) to build your add-on.
*packager* requires a POSIX environment.

To build @addon-name@:

```sh
$ release.sh -m pkgmeta.yaml -d -z
```

To symlink @addon-name@ to your `AddOns` during development:

```bat
mklink @addon-name@ <path to your WoW installation>\_retail_\Interface\AddOns\@addon-name@
```

## Publishing

Pushing a Git tag will trigger the `release` workflow, which will package and upload @addon-name@ to GitHub, CurseForge and WoWInterface.
For the last two, you will need to generate an API token for uploading. You can generate a CurseForge API token from https://authors.curseforge.com/account/api-tokens, and WoWInterface token from https://www.wowinterface.com/downloads/filecpl.php?action=apitokens.
Add the tokens as separate secrets in the settings of your repo with a `name` value of `CF_API_KEY` and `WOWI_API_TOKEN`, respectively.

## Community

You can ask questions on the [WoW UI Dev](https://discord.gg/sVQCHr5) Discord server.  You will also find an up-to-date list of development resources there.

## Credits

The boilerplate for @addon-name@ was generated in VSCode using the WoW Addon Tools (WAT) extension. WAT uses [wow-addon-tempalte](https://github.com/ChrisKader/wow-addon-template), a fork of [wow-addon-tempalte](https://github.com/layday/wow-addon-template) maintained by [layday](https://github.com/layday).
