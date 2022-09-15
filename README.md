# Electron Webclient Template

<img src="build/icons/128x128.png" alt="logo" height="80" align="center" />

The electron desktop webclient template(Based on [Prospect Mail](https://github.com/julian-alarcon/prospect-mail))

Available for Linux, Windows and macOS.

### Architecture components

The main software architecture components and their versions are this:

* [Node.js](https://nodejs.org/en/) version: 16.13.x
* [yarn](https://yarnpkg.com/) version: 1.22.x or newer
* [electron](http://electronjs.org/) version: 16.0.x
* [electron-builder](https://www.electron.build/) version: 22.14.x
* [electron-settings](https://github.com/nathanbuchar/electron-settings) version: 4.0.2

## Build

Clone the repository and run in development mode. (You need to have
[git](https://git-scm.com/) , node and yarn) installed)

```bash
git clone https://github.com/RuiNiles/electron-webclient-template.git
cd electron-webclient-template
yarn
yarn start
```

Build the application for linux

```bash
yarn run dist:linux
```

This will build an AppImage, deb and snap files in the dist folder. This files
can be run in most popular linux distributions.

Is possible to specify the snap or AppImage build type using running this:

```bash
yarn run dist:linux:snap
```

Build the application for Mac (It works in versions 10.14 and 10.15)

```bash
yarn run dist:mac
```

### Install developer artifact

Once it was builded, or using the release files available, you can install the
files using [AppImage process](https://docs.appimage.org/user-guide/faq.html#question-how-do-i-run-an-appimage),
using .deb ```sudo dpkg -i prospect-mail_x.y.z_arch.deb``` or using the snap
file ```sudo snap install prospect-mail_x.y.z_arch.snap --dangerous```.

## Release to Public

With the specific permissions on Github, to create a new release follow the
steps defined by [action-electron-builder](https://github.com/samuelmeuli/action-electron-builder)

1. Define version in package.json. E.g. `0.4.0`
1. Add commit with changes. E.g. `git commit -am v0.4.0`
1. Tag the commit. E.g. `git tag v0.4.0`. Don't forget the `v` as suffix of the
version.
1. Push changes including tags `git push && git push --tags`

## Manual release to Snapstore

```sh
snapcraft login
snapcraft upload --release=edge prospect-mail_x.y.z_arch.snap
```

## License

[MIT](https://github.com/julian-alarcon/prospect-mail/blob/master/LICENSE) by
[Julian Alarcon](https://desentropia.com) based on work on
[electron-outlook](https://github.com/eNkru/electron-outlook) by
[Howard J](https://enkru.github.io/)
