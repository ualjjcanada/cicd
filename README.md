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

- Install Antora locally: en la  carpeta con el playbook de Antora
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
  - Install http server: 

- Run Antora: 
```
npx antora local-antora-playbook.yml --fetch
```



## Extensions
- An Antora extension that adds a self-hosted search powered by Lunr to an Antora site: https://gitlab.com/antora/antora-lunr-extension
- Install search powered: `npm i @antora/lunr-extension`
- http server: 

## Extra
- Add icons to admonition labels: https://blog.yuzutech.fr/antora-admonitions-icons/
- Tabs and groups (not default UI): https://lightbend.github.io/antora-supplemental-ui-lightbend-theme/build/site/groups.html