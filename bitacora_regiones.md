# Bitácora · Rueda Libre · Regiones semánticas

## 1. Esquemas de regiones (antes de tocar el código)

### index.html
```
body
├── header
│   ├── p > strong "Rueda Libre"
│   └── nav (principal)
│       └── ul: Inicio · Tarifas y rutas · Reservas
├── main
│   ├── h1 + img portada + p introductorio (enlace a #encuentranos)
│   ├── section ¿Quiénes somos?            (h2)
│   ├── section Nuestros servicios         (h2)
│   │   ├── article Alquiler de bicicletas (h3)
│   │   ├── article Recorridos guiados     (h3)
│   │   └── article Taller básico          (h3)
│   ├── section ¿Cómo alquilar?            (h2)
│   │   └── section Beneficios             (h3)
│   └── section#encuentranos Encuéntranos  (h2)
└── footer
```

### tarifas.html
```
body
├── header (logo + nombre + nav principal)
├── main
│   ├── h1 + p introductorio
│   ├── section Tarifas de alquiler de bicicletas   (h2 + table)
│   ├── section#recorridos-guiados Tarifas de recorridos guiados (h2 + table)
│   └── section Información importante              (h2)
│       └── aside ¿Qué debes llevar?                (h3 + ul)  ← complementario
└── footer
```

### reservas.html
```
body
├── header (nombre + nav principal)
├── main
│   ├── h1 + p introductorio
│   ├── section Formulario de reserva (h2 + form con fieldsets)
│   └── aside Horario de atención     (h2 + dl)  ← complementario
└── footer
```

## 2. Cambios realizados

- **index.html**: era el único sin regiones. Se añadió `header` (nombre + `nav` con `aria-label="Navegación principal"`), `main`, `footer` (ya existía el bloque final, ahora está fuera de `main`). Cada bloque temático pasó a `section`, cada servicio a `article`, y *Beneficios* quedó como `section` anidada dentro de *¿Cómo alquilar?* porque es un h3.
- **tarifas.html y reservas.html**: ya cumplían con todos los requisitos (header, nav principal, un `main`, tablas/formulario en `section`, `aside` para lo complementario, `footer`). No se modificaron, y se conservaron intactos tus comentarios.

## 3. Decisiones que conviene recordar

- **div y span**: no había ninguno en las tres páginas y no se añadió ninguno, así que no hay excepciones que justificar.
- **Nombre del negocio en el header de index**: se agregó `<p><strong>Rueda Libre</strong></p>` para que sea igual que en las otras dos páginas. El h1 se quedó en `main` porque es el título del contenido propio de la página.
- **Intro de index**: h1, imagen y párrafo van directos en `main` sin `section`, porque el h1 ya es su encabezado.
- **`aside` dentro de `main`**: en tarifas y reservas es contenido complementario del contenido de la página, por eso va dentro de `main` y no en el `footer`.

## 4. Verificación

| Comprobación | index | tarifas | reservas |
|---|---|---|---|
| Un solo `main` | Sí | Sí | Sí |
| Jerarquía de encabezados sin cambios | Sí (h1, h2, h2, h3×3, h2, h3, h2) | Sí | Sí |
| Enlaces idénticos a los originales | Sí | sin cambios | sin cambios |
| Ancla `#encuentranos` existe | Sí (`section#encuentranos`) | n/a | n/a |
| Etiquetas balanceadas | Sí | Sí | Sí |
| `div`/`span` | 0 | 0 | 0 |

Pendiente por revisar en tu equipo: las rutas relativas (`paginas/…`, `../index.html`, `img/…`) asumen la estructura `index.html` en la raíz con carpetas `paginas/` e `img/`. Los archivos subidos están en una sola carpeta y las imágenes no se subieron, así que eso no se pudo probar abriendo los enlaces.

## 5. Observaciones fuera del alcance (no modificadas)

- reservas.html: el checkbox de datos personales tiene `id="Tratamiento de datos personales"`, que contiene espacios y no es un id válido; el `label for` no se asocia con el checkbox. Además dice "politícas" y "Acepta" (en el otro checkbox es "Acepto").
- reservas.html: el fieldset "Plan" está bien cerrado pero mal indentado, y `cantidad` y `recorrido` quedan dentro de "Plan".
- tarifas.html: tu comentario dice que el `aside` es como un pie de página; en realidad es contenido complementario (el pie de página es `footer`).
