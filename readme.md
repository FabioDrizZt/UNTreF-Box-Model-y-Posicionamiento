# Box Model y Posicionamiento en CSS

## Box Model (Modelo de Caja)

El **Box Model** es el modelo fundamental que utiliza CSS para representar y manipular los elementos en una página web. Cada elemento se representa como una caja rectangular compuesta por varias capas:

- **Content (Contenido):** Es el área donde se muestra el contenido (texto, imágenes, etc.).
- **Padding (Relleno):** Espacio entre el contenido y el borde de la caja.
- **Border (Borde):** El borde que rodea el padding (y el contenido).
- **Margin (Margen):** Espacio externo entre el borde de la caja y otros elementos.

### Propiedad `box-sizing`

Por defecto, el ancho y alto de un elemento solo incluyen el área de contenido. Si se agrega padding o border, el tamaño total aumenta. Usando `box-sizing: border-box;`, el padding y el border se incluyen dentro del ancho y alto definidos, facilitando el diseño.

```css
* {
  box-sizing: border-box;
}
```

### Ejemplo aplicado

En este repositorio, los elementos `<section>` tienen varias propiedades del Box Model:

```css
section {
  background: #09f;
  width: 120px;
  height: 100px;
  padding-left: 10px;
  padding-top: 10px;
  border-top: solid red 5px;
  border-right: double green 7px;
  border-bottom: dotted purple 10px;
  border-left: outset rgb(43, 43, 148) 13px;
  border-top-right-radius: 10px;
  border-top-left-radius: 10px;
  margin-top: 10px;
  margin-bottom: 20px;
  margin-left: 10px;
  margin-right: 10px;
  overflow: auto;
  box-shadow: 0 4px 4px grey;
}
```

- **padding-left/top:** Añade espacio interno.
- **border-***: Diferentes estilos y grosores de borde.
- **margin-***: Espacio externo entre cajas.
- **box-shadow:** Sombra para dar profundidad.

## Posicionamiento en CSS

El posicionamiento permite controlar cómo y dónde se ubican los elementos en la página. Los valores más comunes de la propiedad `position` son:

- **static:** Valor por defecto. El elemento sigue el flujo normal del documento.
- **relative:** El elemento se posiciona relativo a su posición original. Permite moverlo usando `top`, `left`, `right`, `bottom`.
- **absolute:** El elemento se posiciona respecto al ancestro posicionado más cercano (que no sea static) o al viewport si no hay ninguno.
- **fixed:** El elemento se posiciona respecto al viewport, permaneciendo fijo aunque se haga scroll.

### Ejemplo aplicado

```css
.relativo {
  background: grey;
  position: relative;
  left: 20px;
  top: 50px;
  z-index: -100;
}

.absoluto {
  position: absolute;
  right: 5px;
  bottom: 15px;
}

.icono-whatsapp {
  position: fixed;
  right: 5px;
  bottom: 5px;
}
```

- `.relativo`: Se mueve 20px a la derecha y 50px hacia abajo desde su posición original.
- `.absoluto`: Se ubica en la esquina inferior derecha del contenedor posicionado más cercano.
- `.icono-whatsapp`: Permanece fijo en la esquina inferior derecha de la pantalla, incluso al hacer scroll.

### Otros conceptos útiles
- **z-index:** Controla la superposición de elementos posicionados.
- **overflow:** Controla cómo se muestra el contenido que desborda la caja.

## Buenas prácticas
- Usar `box-sizing: border-box;` para facilitar el cálculo de tamaños.
- Evitar el uso excesivo de `position: absolute` o `fixed` para no romper el flujo natural del documento.
- Utilizar márgenes y paddings para separar visualmente los elementos.

---

Este repositorio es un ejemplo práctico para experimentar con el Box Model y el posicionamiento en CSS. Modifica los valores y observa cómo cambian los elementos en la página para afianzar los conceptos.
