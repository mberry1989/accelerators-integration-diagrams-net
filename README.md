[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

[![Discord][discord-shield]][discord-url]


# Kontent.ai integration with diagrams.net

This integration contains a [custom element](https://kontent.ai/learn/tutorials/develop-apps/integrate/content-editing-extensions/) that you can use in Kontent.ai to create and edit diagrams in diagrams.net directly from the Kontent.ai app.
The custom element stores the created diagram in the `xml` format and a data url to use it on your site.

![demo-gif](docs/demo.gif)

# Getting Started

The integration is created with [Create React App](https://create-react-app.dev/). 

First you will need to install npm dependencies with `npm install`. 
Then use `npm run build` to build the integration or `npm run start` to start a local development server. 
See https://create-react-app.dev/docs/available-scripts for more scripts.

You can also provide a [configuration](#Configuration) to the element, but it is entirely optional.

> The diagrams.net editor is opened in a new tab so that you have enough space for your diagram.
> Changes in the editor are auto-saved to Kontent.ai.
> However, if you leave the item editing or switch to a different content group in the Kontent.ai tab, the connection breaks and further changes to the diagram won't be saved.

## Configuration

You can provide an optional configuration. See the example bellow.
https://github.com/JiriLojda/integration-diagrams-net/blob/8f9d0d62ae2efed67da746146e63400a464dc6d7/src/constants/readmeSnippets.ts#L3-L14

## Deploy

To use the custom element you need to deploy it.

Netlify has made this easy. If you click the deploy button below, it will guide you through the process of deploying it and leave you with a copy of the repository in your account as well.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/JiriLojda/integration-diagrams-net)

> The repository has the [continuous delivery configuration](./.github/workflows/deploy.yml) using GitHub Actions being triggered by the new release and releasing to `gh-pages` branch. This setup is used for internal purposes. If you want to use the custom element, the recommended way is to fork the repository, make a code review, and deploy the repository on your own.

## Saved value

This is an example of a value saved in the custom element that can be used on your site. Keep in mind that it is serialized into string.
https://github.com/JiriLojda/integration-diagrams-net/blob/8f9d0d62ae2efed67da746146e63400a464dc6d7/src/constants/readmeSnippets.ts#L16-L23

# Known Issues

## Value is too large for Kontent.ai with a custom font used in the diagram.

When using the `previewImageFormat: "svg"` and a custom font in the diagram, diagrams.net includes the whole font in the data-url for preview.
This makes it (and the value as the data-url is saved as well) too large.
To avoid the problem, set `previewImageFormat: "png"` in your configuration. Png's don't have this problem, but are usually bigger so the svg is the default.

# Contributing

For Contributing please see  [`CONTRIBUTING.md`](CONTRIBUTING.md) for more information.

# License

Distributed under the MIT License. See [`LICENSE.md`](./LICENSE.md) for more information.


[contributors-shield]: https://img.shields.io/github/contributors/JiriLojda/integration-diagrams-net.svg?style=for-the-badge
[contributors-url]: https://github.com/JiriLojda/integration-diagrams-net/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/JiriLojda/integration-diagrams-net.svg?style=for-the-badge
[forks-url]: https://github.com/JiriLojda/integration-diagrams-net/network/members
[stars-shield]: https://img.shields.io/github/stars/JiriLojda/integration-diagrams-net.svg?style=for-the-badge
[stars-url]: https://github.com/JiriLojda/integration-diagrams-net/stargazers
[issues-shield]: https://img.shields.io/github/issues/JiriLojda/integration-diagrams-net.svg?style=for-the-badge
[issues-url]:https://github.com/JiriLojda/integration-diagrams-net/issues
[license-shield]: https://img.shields.io/github/license/JiriLojda/integration-diagrams-net.svg?style=for-the-badge
[license-url]:https://github.com/JiriLojda/integration-diagrams-net/blob/master/LICENSE.md
[discord-shield]: https://img.shields.io/discord/821885171984891914?color=%237289DA&label=Kontent.ai%20Discord&logo=discord&style=for-the-badge
[discord-url]: https://discord.com/invite/SKCxwPtevJ
