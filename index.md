title: Cata CSS
author:
  name: Raúl Hernández
  twitter: raulghm
  url: https://github.com/raulghm
output: index.html
controls: true
style: style.css
theme: juanbrujo/cleaver-beerjs

--

# Cata CSS
## Base and low level components

--

# Los contras de CSS (o del mundo CSS)

* No depender de un preprocesador (SASS, LESS, Stylus)
* Scope, naming, conventions
* Integración con diferentes stacks o frameworks
* Portabilidad del código
* Mantención y escalabilidad

--

# ¿Por qué sistematizar CSS?
## o modularizar...

--

# Core features

* PostCSS
* Orientado a componentes (scope)
* Testeable
* Extendible (npm)
* Themification

--

# Scope
## BEM + SuitCSS

```  
.MyComponent {}
.MyComponent.is-animating {}
.MyComponent--modifier {}

.MyComponent-part {}
.MyComponent-anotherPart {}
```

<img src="http://snappyimages.nextwavesrl.netdna-cdn.com/img/d2d3afb7038d03a765e4d377cfd84bc5.png" alt="">
--

# Módulos CSS + NPM
## Simples modulos encapsulados

<img src="http://snappyimages.nextwavesrl.netdna-cdn.com/img/1965e411cf9cde2416afcfa4839296b4.png" alt="image">

--

# CSS Testing
## Lint, namespacing, order, reglas globales, etc.

```
npm install cata-components-button
npm run lint
```

https://github.com/raulghm/cata-components-button
--

# Cata
## Starting...


Terminal
```bash
yarn add cata-base cata-variables cata-breakpoints cata-components-button
```

CSS
```css
@import "cata-base";
@import "cata-variablaes";
@import "cata-breakpoints";

...
```
--

# Theming / extending

```
@import "cata-components-button";

.Button--default {
  background-color: #eee;
  color: #444;
  border-color: #d9d9d9 #d9d9d9 #ccc;
  border-radius: 2px;
}
```

--

# CSS Pre procesador

Webpack / Vue

```
{
  loader: 'postcss-loader',
  options: {
    ident: 'postcss',
    plugins: (loader) => [
      require('postcss-import')({ root: loader.resourcePath }),
      require('postcss-cssnext')(),
      require('autoprefixer')(),
      require('cssnano')()
    ]
  }
}
```

* https://github.com/suitcss/preprocessor
* https://gist.github.com/michael-ciniawsky/df6f6ee1ed76c348c1849178107f08a9
--


# Resources

* http://cssnext.io
* https://postcss.org
* https://github.com/raulghm/cata-*