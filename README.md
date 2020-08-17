<p align="center">
   <a href="https://github.com/controlandy/idm/blob/master/README.md">
    <img src="idm.png" alt="IDM logo">
  </a>
</p>
<h3 align="center">Red hat Identity Management</h3>
<p align="center">
Workshop elaborado para el cliente ABC  <br>
  <a href="https://www.opennova.pe/"><strong>OpenNova Training </strong></a>
  <br>
  <br>
</p>


## Alcance

Manual de procedimientos del workshop de la solución Red Hat Identity Management versión X sobre plataforma Red Hat Enterprise Linux 8.2

## Tabla de cotenidos

- [Requisitos](#requisitos)
- [Proceso de instalación](#proceso-de-instalación)
- [Configuración del servicio](#configuración-del-servicio)
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Community](#community)
- [Versioning](#versioning)
- [Creators](#creators)
- [Thanks](#thanks)
- [Copyright and license](#copyright-and-license)


## Requisitos

Para la ejecución del laboratorio de IDM se necesitan cumplir los siguientes requerimientos de sistema operativo:
- Sistema operativo RHEL 8.2
- Suscripción activa o repositorio con el ISO de RHEL activo
- Dominio reservado para la instalación del servicio
- Dimensionamiento de hardware segón la transaccionalidad del servicio, revisar [IDM]( https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/installing_identity_management/preparing-the-system-for-ipa-server-installation_installing-identity-management)

## Proceso de instalación

El proceso de instalación inicia con la habilitación de los repositorios de sistema operativo `rhel-8-for-x86_64-baseos-rpms` y `rhel-8-for-x86_64-appstream-rpms` con los comandos:

`# subscription-manager repos --enable=rhel-8-for-x86_64-baseos-rpms`

`# subscription-manager repos --enable=rhel-8-for-x86_64-appstream-rpms`


En caso de no contar con una suscripción activa, se puede utilizar un repositorio creado a partir del ISO de RHEL 8.2 editando el archivo de configuración de repositorio en la ruta `/etc/yum.repos.d/rhel.repo` con el siguiente contenido:
<br>`[BaseOS]`
<br>`name=BaseOS`
<br>`enabled=1`
<br>`baseurl=<ruta de la ISO montada>/BaseOS`
<br>`gpgcheck=1`
<br>`gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release`
<br>`###`
<br>`[AppStream]`
<br>`name=AppStream`
<br>`enabled=1`
<br>`baseurl=<ruta de la ISO montada>/AppStream`
<br>`gpgcheck=1`
<br>`gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release`

El comando `yum repolist` nos permitira validar la disponibilidad de los repositorios ya sean por suscripción o por ISO

`# yum repolist`

Al validar la disponibilidad de los repositorios se podra activar el módulo de IDM con:

`# yum module enable idm:DL1`

`# yum distro-sync`

Finalmente, el proceso de instalación se podrá¡ iniciar con el comando:

`yum module install idm:DL1/server`

Considerar que el proceso de instalación puede realizarse con diferentes modulos además del servidor base, también existen otros modulos:
<br>- server
<br>- dns
<br>- adtrust
<br>- client

Demostración de la instalación con ISO de RHEL 8.2 aqui:

Demostración de la instalación con subscripciÃ³n de RHEL 8.2 aqui:




## Configuración del servicio

Within the download you'll find the following directories and files, logically grouping common assets and providing both compiled and minified variations. You'll see something like this:

```text
bootstrap/
â””â”€â”€ dist/
    â”œâ”€â”€ css/
    â”‚   â”œâ”€â”€ bootstrap-grid.css
    â”‚   â”œâ”€â”€ bootstrap-grid.css.map
    â”‚   â”œâ”€â”€ bootstrap-grid.min.css
    â”‚   â”œâ”€â”€ bootstrap-grid.min.css.map
    â”‚   â”œâ”€â”€ bootstrap-reboot.css
    â”‚   â”œâ”€â”€ bootstrap-reboot.css.map
    â”‚   â”œâ”€â”€ bootstrap-reboot.min.css
    â”‚   â”œâ”€â”€ bootstrap-reboot.min.css.map
    â”‚   â”œâ”€â”€ bootstrap-utilities.css
    â”‚   â”œâ”€â”€ bootstrap-utilities.css.map
    â”‚   â”œâ”€â”€ bootstrap-utilities.min.css
    â”‚   â”œâ”€â”€ bootstrap-utilities.min.css.map
    â”‚   â”œâ”€â”€ bootstrap.css
    â”‚   â”œâ”€â”€ bootstrap.css.map
    â”‚   â”œâ”€â”€ bootstrap.min.css
    â”‚   â””â”€â”€ bootstrap.min.css.map
    â””â”€â”€ js/
        â”œâ”€â”€ bootstrap.bundle.js
        â”œâ”€â”€ bootstrap.bundle.js.map
        â”œâ”€â”€ bootstrap.bundle.min.js
        â”œâ”€â”€ bootstrap.bundle.min.js.map
        â”œâ”€â”€ bootstrap.esm.js
        â”œâ”€â”€ bootstrap.esm.js.map
        â”œâ”€â”€ bootstrap.esm.min.js
        â”œâ”€â”€ bootstrap.esm.min.js.map
        â”œâ”€â”€ bootstrap.js
        â”œâ”€â”€ bootstrap.js.map
        â”œâ”€â”€ bootstrap.min.js
        â””â”€â”€ bootstrap.min.js.map
```

We provide compiled CSS and JS (`bootstrap.*`), as well as compiled and minified CSS and JS (`bootstrap.min.*`). [source maps](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) (`bootstrap.*.map`) are available for use with certain browsers' developer tools. Bundled JS files (`bootstrap.bundle.js` and minified `bootstrap.bundle.min.js`) include [Popper](https://popper.js.org/).


## Bugs and feature requests

Have a bug or a feature request? Please first read the [issue guidelines](https://github.com/twbs/bootstrap/blob/main/.github/CONTRIBUTING.md#using-the-issue-tracker) and search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](https://github.com/twbs/bootstrap/issues/new).


## Documentation

Bootstrap's documentation, included in this repo in the root directory, is built with [Hugo](https://gohugo.io/) and publicly hosted on GitHub Pages at <https://v5.getbootstrap.com/>. The docs may also be run locally.

Documentation search is powered by [Algolia's DocSearch](https://community.algolia.com/docsearch/). Working on our search? Be sure to set `debug: true` in `site/assets/js/src/search.js` file.

### Running documentation locally

1. Run `npm install` to install the Node.js dependencies, including Hugo (the site builder).
2. Run `npm run test` (or a specific npm script) to rebuild distributed CSS and JavaScript files, as well as our docs assets.
3. From the root `/bootstrap` directory, run `npm run docs-serve` in the command line.
4. Open `http://localhost:9001/` in your browser, and voilÃ .

Learn more about using Hugo by reading its [documentation](https://gohugo.io/documentation/).

### Documentation for previous releases

You can find all our previous releases docs on <https://v5.getbootstrap.com/docs/versions/>.

[Previous releases](https://github.com/twbs/bootstrap/releases) and their documentation are also available for download.


## Contributing

Please read through our [contributing guidelines](https://github.com/twbs/bootstrap/blob/main/.github/CONTRIBUTING.md). Included are directions for opening issues, coding standards, and notes on development.

Moreover, if your pull request contains JavaScript patches or features, you must include [relevant unit tests](https://github.com/twbs/bootstrap/tree/main/js/tests). All HTML and CSS should conform to the [Code Guide](https://github.com/mdo/code-guide), maintained by [Mark Otto](https://github.com/mdo).

Editor preferences are available in the [editor config](https://github.com/twbs/bootstrap/blob/main/.editorconfig) for easy use in common text editors. Read more and download plugins at <https://editorconfig.org/>.


## Community

Get updates on Bootstrap's development and chat with the project maintainers and community members.

- Follow [@getbootstrap on Twitter](https://twitter.com/getbootstrap).
- Read and subscribe to [The Official Bootstrap Blog](https://blog.getbootstrap.com/).
- Join [the official Slack room](https://bootstrap-slack.herokuapp.com/).
- Chat with fellow Bootstrappers in IRC. On the `irc.freenode.net` server, in the `##bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-5`](https://stackoverflow.com/questions/tagged/bootstrap-5)).
- Developers should use the keyword `bootstrap` on packages which modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/browse/keyword/bootstrap) or similar delivery mechanisms for maximum discoverability.


## Versioning

For transparency into our release cycle and in striving to maintain backward compatibility, Bootstrap is maintained under [the Semantic Versioning guidelines](https://semver.org/). Sometimes we screw up, but we adhere to those rules whenever possible.

See [the Releases section of our GitHub project](https://github.com/twbs/bootstrap/releases) for changelogs for each release version of Bootstrap. Release announcement posts on [the official Bootstrap blog](https://blog.getbootstrap.com/) contain summaries of the most noteworthy changes made in each release.


## Creators

**Mark Otto**

- <https://twitter.com/mdo>
- <https://github.com/mdo>

**Jacob Thornton**

- <https://twitter.com/fat>
- <https://github.com/fat>


## Thanks

<a href="https://www.browserstack.com/">
  <img src="https://live.browserstack.com/images/opensource/browserstack-logo.svg" alt="BrowserStack Logo" width="192" height="42">
</a>

Thanks to [BrowserStack](https://www.browserstack.com/) for providing the infrastructure that allows us to test in real browsers!


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/bootstrap#sponsor)]

[![OC sponsor 0](https://opencollective.com/bootstrap/sponsor/0/avatar.svg)](https://opencollective.com/bootstrap/sponsor/0/website)
[![OC sponsor 1](https://opencollective.com/bootstrap/sponsor/1/avatar.svg)](https://opencollective.com/bootstrap/sponsor/1/website)
[![OC sponsor 2](https://opencollective.com/bootstrap/sponsor/2/avatar.svg)](https://opencollective.com/bootstrap/sponsor/2/website)
[![OC sponsor 3](https://opencollective.com/bootstrap/sponsor/3/avatar.svg)](https://opencollective.com/bootstrap/sponsor/3/website)
[![OC sponsor 4](https://opencollective.com/bootstrap/sponsor/4/avatar.svg)](https://opencollective.com/bootstrap/sponsor/4/website)
[![OC sponsor 5](https://opencollective.com/bootstrap/sponsor/5/avatar.svg)](https://opencollective.com/bootstrap/sponsor/5/website)
[![OC sponsor 6](https://opencollective.com/bootstrap/sponsor/6/avatar.svg)](https://opencollective.com/bootstrap/sponsor/6/website)
[![OC sponsor 7](https://opencollective.com/bootstrap/sponsor/7/avatar.svg)](https://opencollective.com/bootstrap/sponsor/7/website)
[![OC sponsor 8](https://opencollective.com/bootstrap/sponsor/8/avatar.svg)](https://opencollective.com/bootstrap/sponsor/8/website)
[![OC sponsor 9](https://opencollective.com/bootstrap/sponsor/9/avatar.svg)](https://opencollective.com/bootstrap/sponsor/9/website)


## Backers

Thank you to all our backers! ðŸ™ [[Become a backer](https://opencollective.com/bootstrap#backer)]

[![Backers](https://opencollective.com/bootstrap/backers.svg?width=890)](https://opencollective.com/bootstrap#backers)


## Copyright and license

Code and documentation copyright 2011â€“2020 the [Bootstrap Authors](https://github.com/twbs/bootstrap/graphs/contributors) and [Twitter, Inc.](https://twitter.com) Code released under the [MIT License](https://github.com/twbs/bootstrap/blob/main/LICENSE). Docs released under [Creative Commons](https://creativecommons.org/licenses/by/3.0/).
=======
# idm

