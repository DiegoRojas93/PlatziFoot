# Platzi Foot

Este proyecto fue realizado por medio del framewok de Tailwindcss y alpine.js.

https://tailwindcss.com/
https://github.com/alpinejs/alpine

https://purgecss.com/
https://cssnano.co/


postcss.config.js
```
const purgecss = require('@fullhuman/postcss-purgecss')

module.exports = {
  plugins:[
    require('tailwindcss'),
    require('autoprefixer'),
    purgecss({
      content: [
        './**/*.html'
        //Para agregar soporte para otro tipo de archivos.
       // './**/*.js',
       // './**/*.vue'
    ],
      //IMPORTANTE: Para el correcto funcionamiento de las pseudo-clases
      defaultExtractor: content => content.match(/[\w-/:]+(?<!:)/g) || []
    }),
  
    require('cssnano')({
      preset: 'default',
    })
  ]
}
```