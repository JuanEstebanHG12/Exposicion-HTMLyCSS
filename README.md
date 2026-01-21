# 📘 Guía básica de HTML y CSS

Este README resume conceptos clave para comenzar a trabajar correctamente con **HTML y CSS**, errores comunes y buenas prácticas.

***Un aprendiz indica que sus estilos CSS no se aplican***

> Explica tu proceso de diagnóstico y acompañammiento paso a paso.
> - Verificaciones de técnicas básicas
> - Revisón del flujo HYML-CSS

---

## 🔗 Cómo linkear el CSS a mi HTML

Para que el CSS funcione, debe estar correctamente enlazado dentro del `<head>` del archivo HTML.

### ✅ Ejemplo correcto (ruta válida)

Estructura del proyecto:

/proyecto

├── index.html

└── style.css


El link correcto es:

```html
<link rel="stylesheet" href="./style.css">
```

❌ Ejemplo incorrecto (ruta inválida)

```
<link rel="stylesheet" href="styles.css">
```

❌ Error común:

- Creamos la arquitectura base

- El nombre es diferente (style.css ≠ styles.css)

- Está en otra carpeta y no se indicó la ruta correcta

---

## 🎯 Selectores CSS y su especificidad

La especificidad define qué estilo se aplica cuando varios selectores apuntan al mismo elemento.

| Tipo de selector     | Ejemplo                      | Peso       |
|--------------------|------------------------------|-----------|
| 🔹 Etiqueta          | `p`                          | Bajo       |
| 🔹 Clase             | `.texto`                     | Medio    |
| 🔹 ID                | `#titulo`                    | Alto     |
| 🔹 Selector complejo | `div > span > p.parrafo`     | Depende  |

🔹 **Selector por Etiqueta**
```
p{
    color: aqua;
}
```
Aplica a todos los `<p>`.

🔹 **Selector por clase**
```
.textColor{
    color: red;
}
<p class="textColor">Texto</p>
```

✔ Más específico que una etiqueta.

🔹 **Selector por ID**
```
#textColor{
    color: purple;
}

<p id="textColor" class="textColor">test</p>
```

⚠️ Un ID debe ser único en el HTML.

🔹 **Selector complejo (más específico)**
```
div > span > p.parrafo {
  color: purple;
}

<div>
  <span>
    <p class="parrafo">Texto</p>
  </span>
</div>
```
✔ Solo se aplica si toda la estructura coincide.


### ⚖️ Sistemas de pesos en selectores CSS
|            Tipo        | Inline styles | ID   | Clase |Etiqueta|
|------------------------|---------------|------|-------|--------|
| 🔹 `p`                 | 0            | 0     |   0    |   1     |
| 🔹 `p.textColor`       | 0            | 0     |    1   |    1    |
| 🔹 `p#textColor`       | 0            | 1     |    0   |    0    |
|🔹`div > span > p.textColor`| 0          | 0     |  1     |     3  |



## ⚠️ Errores comunes por los que no funciona el CSS
❌ 1. CSS mal linkeado

   - Ruta incorrecta

   - Archivo no existe

   - Error de nombre

❌ 2. Error de escritura
```
.colr {
  color: red;
}
```

➡️ color está mal escrito

❌ 3. El selector no coincide con el HTML
```
.texto {
  color: blue;
}

<p class="text">Hola</p>
```

❌ .texto ≠ .text

❌ 4. Otro selector tiene más peso
```
p {
  color: blue;
}
```
```

#especial {
  color: red;
}
```
➡️ Gana el id por mayor especificidad.



## ✅ Recomendaciones finales

✔ Usa clases antes que IDs

✔ Mantén nombres claros y consistentes

✔ Revisa la consola del navegador

