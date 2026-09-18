[README.md](https://github.com/user-attachments/files/32365887/README.md)
# Rumbo a la UNPRG

App web para preparar el examen de admisión de la Universidad Nacional Pedro Ruiz Gallo.

- **82 clases** de teoría cubriendo las 17 áreas del temario oficial
- **400 preguntas** con explicación, incluidas 179 tomadas de exámenes de admisión reales (2003–2017)
- **Simulacro** de 40 preguntas en 60 minutos, con resultado desglosado por área
- **Temario oficial** completo con casillas para marcar avance
- Racha diaria, puntos y repaso automático de los errores

Todo está en un solo archivo `index.html`, sin servidor ni base de datos. El avance se guarda en el navegador de cada persona.

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio nuevo en GitHub (puede ser público).
2. Sube el archivo `index.html` a la raíz del repositorio.
3. Entra a **Settings** → **Pages**.
4. En *Source* elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guarda.
5. Espera un par de minutos. El link queda así:

```
https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/
```

Ese link se puede compartir con cualquiera y abrir desde cualquier celular.

## Sobre el avance guardado

El progreso (clases leídas, temas marcados, racha, puntos, errores y simulacros) se guarda con `localStorage`, que es el almacenamiento propio del navegador.

Esto significa que:

- Cada persona que abra el link tiene su propio avance, independiente del de los demás.
- El avance sobrevive al cerrar el navegador y apagar el celular.
- El avance **no** se sincroniza entre dispositivos: si abre el link en el celular y en la laptop, cada uno lleva su propia cuenta.
- Si borra los datos de navegación del sitio o usa modo incógnito, el avance se pierde.

Recomendación: usar siempre el mismo navegador y el mismo dispositivo, y agregar el link a la pantalla de inicio del celular (en el menú del navegador, *Agregar a pantalla de inicio*). Así se abre como si fuera una app.

## Personalizar

Todo el contenido está dentro de `index.html`, al inicio del bloque `<script>`:

- `AREAS` — las 17 áreas del temario
- `TEMARIO` — la lista de temas de cada área
- `BANCO` — las preguntas, en el formato `[área, enunciado, opciones, índice de la respuesta correcta, explicación]`
- `EXAMENES` — las preguntas de exámenes anteriores, con un sexto campo para el año
- `CLASES` — la teoría, en el formato `[título, contenido]`

Dentro del contenido de una clase, cada línea se interpreta así: `#` al inicio es un subtítulo, `-` es una viñeta, `>` es un recuadro destacado, y cualquier otra línea es un párrafo.

Para cambiar los colores, edita las variables CSS en `:root` (tema claro) y en los dos bloques `data-theme="dark"` (tema oscuro).
