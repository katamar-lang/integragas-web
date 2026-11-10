# Integragas Colombia SAS · página web

Página web de **Integragas Colombia SAS** con su catálogo de gasodomésticos Haceb (calentadores, estufas, hornos y campanas).
No muestra precios: cada producto tiene un botón **"Cotizar por WhatsApp"** que abre WhatsApp con un mensaje ya escrito.

Es una página estática: un solo archivo `index.html` (con el CSS y el JavaScript adentro) y la carpeta `assets/`. No necesita instalar nada ni compilar.

```
index.html                  la página
assets/logo-integragas.svg  el logo
assets/products/            fotos de los productos
```

## Cómo editar los datos de la empresa

1. Abre `index.html`.
2. Busca `const BUSINESS = {` (está al inicio del `<script>`, casi al final del archivo).
3. Cambia el texto que está entre comillas:

| Campo | Qué es |
|---|---|
| `name` | Nombre completo (sale en el pie de página) |
| `shortName` | Nombre corto (sale arriba, junto al logo) |
| `tagline` | Frase bajo el nombre |
| `whatsapp` | Número de WhatsApp (ver abajo) |
| `whatsappMessage` | Mensaje que aparece escrito al abrir WhatsApp |
| `logo` | Ruta del logo, por ejemplo `assets/logo-integragas.png` |
| `city`, `address`, `hours`, `email`, `nit` | Ciudad, dirección, horario, correo y NIT. **Si un campo queda vacío (`""`), no se muestra.** |

4. Guarda el archivo y súbelo a GitHub. La página se actualiza sola en uno o dos minutos.

## Cómo cambiar el número de WhatsApp

En `BUSINESS.whatsapp` escribe el código del país (Colombia = `57`) seguido del número, **sin espacios, sin `+` y sin guiones**:

```js
whatsapp: "573213096276",
```

Todos los botones de WhatsApp de la página usan ese número.

## Cómo cambiar o agregar productos

Busca `const PRODUCTS = [`. Cada producto es un bloque `{ ... }` con:

- `name`: nombre del producto
- `category`: categoría (los botones de filtro se crean solos con las categorías)
- `text`: descripción corta
- `image`: ruta de la foto, por ejemplo `"assets/products/calentador.jpeg"`. Si queda vacía, se muestra un dibujo.
- `icon`: dibujo que se usa cuando no hay foto: `heater`, `tank`, `stove`, `cooktop`, `oven` o `hood`

Para agregar un producto, copia un bloque, pégalo debajo (separado por una coma) y cambia los textos.

**No escribas precios:** la página está pensada para cotizar por WhatsApp.
