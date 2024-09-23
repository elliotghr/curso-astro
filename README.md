## Islas

Tipo de arq en el frontend (sobre todo estaticas) donde se pueden segmentar porciones dinamicas, esto optimiza el js al no convertir toda la pagina en dinamica, sino solo ciertas areas y componentes

## Estructura del proyecto

Contamos con dos carpetas principales, _./public_ y _./src_,

### Carpeta src

En ./src contamos con un archivo _env.d.ts_ que trae la configuración de TS al proyecto.
En la carpeta ./src/pages contamos con el _index.astro_ de la aplicación, en este archivo contamos con una sintaxis de Astro (similar JSX).

Al inicio del archivo contamos con un bloque de "---" donde se importan los componentes y también podemos escribir nuesrto código js o ts, definir las props, etc.

A continuación tenemos el código HTML envuelto en un componente (parecido a los de react) con su propiedad title definida.

Al final contamos con el bloque de estilos del sitio. Estos estilos tienen su propio _"scope"_, esto quiere deir que los estilos de una regla main{} solo afectan al _main_ del mismo componente donde se alojan, no aplican a otros main del DOM.

En la carpeta ./src/layout contamos con componentes especiales que envuelven parte de nuestra aplicación. Estos componentes pueden recibir propiedades definidas en su propio archivo defininedo una _interface_:

```js
interface Props {
  title: string;
}

const { title } = Astro.props;
```

Podemos acceder a estas propiedades del objeto global _Astro_.
También podemos definir estilos globales añadiendo "is:global" a la etiqueda style.

```html
<style is:global></style>
```

Al final tenemos la carpeta ./src/components, en donde se alojarán todos los componentes de nuestra aplicaión. A diferencia de react no tenemos que repetir tanto código al exportarlos y toma ciertas funcionalidades de JSX.
