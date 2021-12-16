# Default - WoW Addon Tools Template

This template is used by the VS Code extension WoW Addon Tools. The primary goal is to provide developers (new and seasoned) with a baseline addon structure that helps enforce as many of the best practices of WoW addon development.

## Included:

- A "starter" addon (`Addon.lua` and `Addon.toc`)
- A GitHub workflow which automates releasing your add-on on GitHub, CurseForge, and WoWInterface, build instructions for *packager*, the de facto add-on build tool
- Basic [Luacheck](https://github.com/mpeterv/luacheck) configuration and an accompanying workflow
- Instructions for [keeping a changelog](https://keepachangelog.com/en/1.0.0/).

## Development
This template encourages the use of [*packager*](https://github.com/BigWigsMods/packager) to maintain the CI workflow for a developers addon.  

*packager* DOES requires a POSIX environment
- Windows users can use [WSL2](https://docs.microsoft.com/en-us/windows/wsl/about)

To build your add-on:

```sh
$ release.sh -m pkgmeta.yaml -d -z
```

To symlink your add-on into `AddOns` during development:

- Windows Command Prompt
    ```bat
    mklink AddonName <path to your WoW installation>\_retail_\Interface\AddOns\AddonName
    ```

- Linux Shell
    ```sh
    $ ln -s $PWD/.release/Addon <path to your WoW installation>/_retail_/Interface/AddOns/Addon
    ```

*Note: Its recommended that you create the symlink in the Windows Command Prompt (cmd.exe).*

## Publishing

Pushing a Git tag will trigger the `release` workflow, which will package and upload your add-on to GitHub, CurseForge and WoWInterface.
For the last two, you will need to generate an API token for uploading.

You can generate a CurseForge API token from https://authors.curseforge.com/account/api-tokens, and a WoWInterface token from https://www.wowinterface.com/downloads/filecpl.php?action=apitokens.

Add the tokens as separate secrets in the settings of your repo with a `name` value of `CF_API_KEY` and `WOWI_API_TOKEN`, respectively.

## Community

You can ask questions on the [WoW UI Dev](https://discord.gg/sVQCHr5) Discord server.  You will also find an up-to-date list of development resources there.

## Credits

This template is a direct fork of [wow-addon-template](https://github.com/layday/wow-addon-template) maintained by [layday](https://github.com/layday)