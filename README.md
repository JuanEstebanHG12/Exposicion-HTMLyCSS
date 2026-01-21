# 📘 Guía básica de HTML y CSS

Este README resume conceptos clave para comenzar a trabajar correctamente con **HTML y CSS**, errores comunes y buenas prácticas.

---

## 🔗 Cómo linkear el CSS a mi HTML

Para que el CSS funcione, debe estar correctamente enlazado dentro del `<head>` del archivo HTML.

### ✅ Ejemplo correcto (ruta válida)

Si tu archivo tiene esta estructura:

/proyecto
├── index.html
└── style.css


El link correcto es:

```html
<link rel="stylesheet" href="./style.css">

❌ Ejemplo incorrecto (ruta inválida)

<link rel="stylesheet" href="styles.css">

❌ Error común:

    El archivo no existe

    El nombre es diferente (style.css ≠ styles.css)

    Está en otra carpeta y no se indicó la ruta correcta

🎯 Selectores CSS y su peso (especificidad)

La especificidad define qué estilo se aplica cuando varios selectores apuntan al mismo elemento.
🟢 Tipos de selectores (de menor a mayor peso)
Selector	Ejemplo	Peso
Etiqueta	p	Bajo
Clase	.texto	Medio
ID	#titulo	Alto
Selector complejo	div > span > p.parrafo	Más específico
🔹 Selector por etiqueta

p {
  color: blue;
}

Aplica a todos los <p>.
🔹 Selector por clase

.parrafo {
  color: green;
}

<p class="parrafo">Texto</p>

✔ Más específico que una etiqueta.
🔹 Selector por ID

#principal {
  color: red;
}

<p id="principal">Texto</p>

⚠️ Un ID debe ser único en el HTML.
🔹 Selector complejo (más específico)

div > span > p.parrafo {
  color: purple;
}

<div>
  <span>
    <p class="parrafo">Texto</p>
  </span>
</div>

✔ Solo se aplica si toda la estructura coincide.
⚠️ Errores comunes por los que no funciona el CSS
❌ 1. CSS mal linkeado

    Ruta incorrecta

    Archivo no existe

    Error de nombre

❌ 2. Error de escritura

.colr {
  color: red;
}

➡️ color está mal escrito
❌ 3. El selector no coincide con el HTML

.texto {
  color: blue;
}

<p class="text">Hola</p>

❌ .texto ≠ .text
❌ 4. Otro selector tiene más peso

p {
  color: blue;
}

#especial {
  color: red;
}

➡️ Gana el id por mayor especificidad.
❌ 5. Uso incorrecto de !important

p {
  color: blue !important;
}

⚠️ Puede romper la lógica de estilos si se usa sin necesidad.
❌ 6. Caché del navegador

A veces el navegador guarda estilos antiguos.

✔ Solución:

    Recargar con Ctrl + F5

    Abrir en incógnito

✅ Recomendaciones finales

✔ Usa clases antes que IDs
✔ Mantén nombres claros y consistentes
✔ Evita !important
✔ Revisa la consola del navegador
✔ Usa el inspector (F12)
