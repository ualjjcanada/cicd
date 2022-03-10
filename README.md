# Antora project
## Install

- Quick install: https://docs.antora.org/antora/latest/install-and-run-quickstart/

- Node: https://docs.antora.org/antora/latest/install/windows-requirements/

```
choco install -y nvm
```

Cerrar y nueva ventana
```
nvm install 16.13.1
nvm on
node -v
npm -v
```

- Install Antora locally: en la carpeta con el playbook de Antora
```
node -e "fs.writeFileSync('package.json', '{}')"
npm i -D -E @antora/cli@3.0.1 @antora/site-generator@3.0.1
```
Verify the antora command is now available by running:
```
npx antora -v
```
- Install extensions
  - Install search powered: `npm i @antora/lunr-extension`
  - Install the http-server package *globally* using npm: `npm i -g http-server`  

- Run Antora: 
```
npx antora local-antora-playbook.yml --fetch
```

- Run http server to preview
```
http-server docs -c-1 -p 5000
```

## Extensions
- An Antora extension that adds a self-hosted search powered by Lunr to an Antora site: https://gitlab.com/antora/antora-lunr-extension
- Install search powered: `npm i @antora/lunr-extension`

Para que funcione la busqueda con esta extensión, hay que configurar el playbook con el valor: 
```
supplemental_files: ./node_modules/@antora/lunr-extension/supplemental_ui
```
Esto genera el arcihvo _/js/search-ui.js
Tras ello, se cambia a tu configuración propia para la UI
```
supplemental_files: ./supplemental-ui
```
Y así  ya se queda creado  el archivo search-ui.js  necesario para que funcione la búsqueda

- http server: https://docs.antora.org/antora/latest/preview-site/

## Extra
- Add icons to admonition labels: https://blog.yuzutech.fr/antora-admonitions-icons/
- Tabs and groups (not default UI): https://lightbend.github.io/antora-supplemental-ui-lightbend-theme/build/site/groups.html

## Throubleshouting

- Error, on Windows: `npm ERR! Unexpected token '.'`

*[Solution](https://github.com/npm/cli/issues/4234#issuecomment-1058261100):*  I had this issue with Node 16.14.0 and NPM 8.3.1. But the real issue was with NVM. I had NVM 1.1.7 but updated to the latest which is currently 1.1.9. Then run `nvm uninstall 16.14.0` followed by `nvm install 16.14.0` and of course `nvm use 16.14.0`
