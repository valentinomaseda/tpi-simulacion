# tpi-simulacion

## Pautas obligatorias del TPI (Causas directas de recuperación)
* **Estructura metodológica:** El informe debe referenciar obligatoriamente los 10 pasos del estudio de simulación.
* **Escenarios y experimentación:** Mínimo dos escenarios (actual vs. hipótesis de mejora). Queda desaprobado si se presenta un único escenario o una única corrida por escenario.
* **Contraste estadístico:** La comparación entre escenarios debe realizarse mediante corridas múltiples y un test de medias formal (con fórmulas y justificación).
* **Software de modelado:** Realizado en AnyLogic.

### Entregable 1 (Informe PDF)
* Redactado exclusivamente en LaTeX con portada, índice, desarrollo, conclusiones y recomendaciones.
* Citar todas las fuentes externas. Prohibido citar Wikipedia (motivo de recuperación).
* El archivo PDF se sube directamente a Classroom (sin links externos a Drive o carpetas compartidas).

### Entregable 2 (Video de exposición)
* **Duración estricta:** Máximo 3 minutos (si supera los 3 min va a recuperación).
* **Sin edición:** No puede estar editado/cortado.
* **Cámara obligatoria:** Deben aparecer todos los integrantes en cámara (ej. vía OBS o reunión de Zoom grabada).
* **Contenido obligatorio:** Diapositivas en Google Slides y extracto de AnyLogic en ejecución.
* Subido a YouTube en modo Oculto (no listar como contenido para niños) y pegar el link en Classroom.

---

## Flujo de Trabajo en Equipo y Configuración

Para trabajar de manera colaborativa sin las limitaciones de Overleaf y evitar conflictos de compilación, se contemplan dos modalidades según el rol en el equipo:

### Configuración del entorno local
Para poder compilar y previsualizar el PDF en Windows dentro de VS Code o Antigravity IDE, cada integrante debe realizar los siguientes pasos:

1. **Instalar el compilador de LaTeX (MiKTeX):**
   * Descargar e instalar **MiKTeX** desde su sitio oficial (`miktex.org`).
   * Abrir la aplicación **MiKTeX Console**, ir a *Settings* y en la opción *"You can decide whether missing packages are to be installed on the fly"*, seleccionar **Yes** para habilitar la descarga automática de paquetes en segundo plano.

2. **Instalar la extensión en el IDE:**
   * En VS Code o Antigravity, ir a la pestaña de extensiones (`Ctrl + Shift + X`).
   * Buscar e instalar **LaTeX Workshop** (desarrollada por James-Yu).

3. **Ajustar la receta de compilación:**
   * Abrir la paleta de comandos con `F1` (o `Ctrl + Shift + P`).
   * Escribir `Preferences: Open User Settings (JSON)` y presionar `Enter`.
   * Agregar dentro de las llaves `{ ... }` la siguiente configuración para forzar el uso directo de `pdflatex` (evita la necesidad de Perl/latexmk y errores con bibtex manual):
     ```json
     "latex-workshop.latex.recipes": [
       {
         "name": "pdflatex",
         "tools": [
           "pdflatex"
         ]
       }
     ],
     "latex-workshop.formatting.latex": "none"
     ```
   * Guardar el archivo (`Ctrl + S`).

4. **Compilar y previsualizar:**
   * Abrir el archivo `.tex` principal del informe.
   * Compilar utilizando el atajo `Ctrl + Alt + B` (o guardando el archivo con `Ctrl + S`).
   * Para ver el visor de PDF integrado al costado del código, hacer clic en el ícono de previsualización arriba a la derecha de la pestaña o usar `Ctrl + Alt + V`.