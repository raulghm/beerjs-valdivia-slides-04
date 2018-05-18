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

# Cata CSS 💜
## Base and low level components

--

# Los contras de CSS (o del mundo CSS) 

* Depender de un preprocesador (SASS, LESS, Stylus)
* Scope, naming, conventions
* Diferentes stacks o frameworks
* Portabilidad del código
* Mantención y escalabilidad

--

# ¿Por qué sistematizar CSS?
## o modularizar...

--

# Nace Cata 💜

--

# Core features ✔️

* PostCSS
* Orientado a componentes (scope)
* Testeable
* Extendible (npm)
* Themification

--

# Scope 👀
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

# Módulos CSS + NPM 📦
## Simples modulos encapsulados

<img src="http://snappyimages.nextwavesrl.netdna-cdn.com/img/1965e411cf9cde2416afcfa4839296b4.png" alt="image">

--

# Cata

<img src="http://snappyimages.nextwavesrl.netdna-cdn.com/img/c99ec57f18dfc0a284e3c2fe8b520954.png" alt="">

--

# Cata + 😀

<img src="http://snappyimages.nextwavesrl.netdna-cdn.com/img/27e90def3a47178fa6b2653171244749.png" alt="">

--

# CSS Testing
## Lint, namespacing, order, reglas globales, etc.

```
npm install cata-components-button
npm run lint
```

https://github.com/raulghm/cata-components-button
--

# Cata 🏁


Terminal
```bash
yarn add cata-base
yarn add cata-variables
yarn add cata-breakpoints
yarn add cata-components-button
```

CSS
```css
@import "cata-base";
@import "cata-variablaes";
@import "cata-breakpoints";

body {...}
```
--

# Theming / extending

```
@import "cata-components-button";

:root {
  --color-button: #bbb;
}

.Button--default {
  background-color: var(--color-button);
  color: #444;
  border-color: #d9d9d9 #d9d9d9 #ccc;
  border-radius: 2px;
}
```

--

# CSS Pre procesador

Webpack / Vue / React / ...

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