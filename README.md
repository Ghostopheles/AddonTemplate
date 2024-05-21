# World of Warcraft Addon Template

This repository is used as a template for creating World of Warcraft addons. Includes a `.pkgmeta` file, and the BigWigs packager.

### Usage

If you're creating a repository using this template, you'll need to grep the repo and change all mentions of `CHANGEME` to fit your addon and usage.

#### Packaging

Setting up the BigWigs packager
- Under repository settings -> Actions, change "Workflow permissions" to "Read and write permissions"
- Under repository settings -> Secrets and variables, create repository secrets for `CF_API_KEY` and `WAGO_API_TOKEN`
    - If you don't want to automatically publish your addon to Curseforge or Wago Addons, you can skip this step and remove the environment variables from [the packaging workflow.](.github/workflows/release.yml)
    - Additionally, you'll want to remove the `X-{site}` TOC directives in your [TOC file](MyAddon.toc)
- In your [TOC file](MyAddon.toc), change the two `X-{site}-ID` directives to point to your Curseforge/Wago project ID.

By default, the packager will package and publish your addon every time you create a tag. To create alpha or beta releases, simply include `alpha` or `beta` somewhere in the tag name.