# Plantilla LaTeX - Plan de Investigación | Carrera de Ingeniería de Software PUCEM

![LaTeX](https://img.shields.io/badge/LaTeX-47A141?style=flat-square&logo=latex&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)
![Status](https://img.shields.io/badge/Status-Activo-brightgreen.svg?style=flat-square)

Una plantilla profesional en LaTeX diseñada para facilitar la redacción de planes de investigación y propuestas de trabajo de titulación bajo los lineamientos de la **Pontificia Universidad Católica del Ecuador Sede Manabí (PUCEM)** - Carrera de Ingeniería de Software.

Esta plantilla está adaptada para cumplir con la estructura y requerimientos de la normativa de la **Unidad de Integración Curricular (UIC) 2023/2025**.

## Características Principales

- **Cumplimiento APA 7ma Edición**: Formato de texto (Times New Roman, doble espaciado, sangría de 1.5em) e idioma español configurados según la normativa.
- **Estructura UIC 2023**: Organizada exactamente en la estructura oficial de 10 puntos requerida para planes de investigación.
- **Tablas Autoajustables y Profesionales**: Tablas de resultados y cronograma formateadas con `booktabs`, diseñadas con `tabular*` para ajustarse exactamente al ancho del texto (`\textwidth`) sin desbordar los márgenes de página.
- **Interlineado de Tablas Controlado**: El interior de las tablas utiliza interlineado simple (`\singlespacing`) para evitar que crezcan verticalmente y generen hojas vacías.
- **Guía de Figuras**: Incluye una sección de inserción de imagen de referencia y su respectiva cita cruzada (`\label` y `\ref`) para guiar a los estudiantes.
- **Bibliografía Automática**: Sistema de referencias basado en BibLaTeX/Biber integrado al índice de forma uniforme y estructurado en salto de página independiente.

## Estructura del Proyecto

```
PUCEM_Plan_Investigacion/
├── main.tex                          # Archivo principal (punto de entrada)
├── PUCEM.sty                         # Archivo de estilos personalizados (títulos, fuentes, APA)
├── referencias.bib                   # Base de datos bibliográfica (archivo BibTeX)
├── 1.-Portada.tex                    # Carátula formal del Plan de Trabajo de Titulación
├── 2.-Contenido.tex                  # Secciones del cuerpo del plan de investigación
└── imagenes/                         # Carpeta de recursos gráficos e imágenes
    ├── PUCEM_LOGO.png                # Logo de la Universidad para la portada
    └── image1.png                    # Imagen de ejemplo para diagramas/arquitecturas
```

## Estructura del Plan de Investigación (10 Puntos de la Normativa)

El archivo `2.-Contenido.tex` está estructurado de la siguiente manera para guiar al estudiante:

1. **Título del proyecto** (Configurado directamente en la carátula `1.-Portada.tex`).
2. **Antecedentes y definición del problema**:
   - *Contexto*: Situación internacional, regional y local de la temática.
   - *Definición del problema*: Diagnóstico de la situación y planteamiento del problema central.
   - *Justificación*: Explicación de la importancia, viabilidad e impacto del proyecto.
3. **Preguntas de investigación**: Pregunta general y preguntas específicas de la investigación.
4. **Objetivos: general y específicos**: Logro global y metas parciales en infinitivo.
5. **Metodología de la investigación**: Detallada de forma secuencial en **8 pasos metodológicos**:
   - *Paso 1: Diseño de la Investigación* (tipo y enfoque)
   - *Paso 2: Alcance de la investigación* (descriptivo, evaluativo, etc.)
   - *Paso 3: Fases del proceso Metodológico* (desglose cronológico de actividades con herramientas)
   - *Paso 4: Población, Muestra y Muestreo* (quiénes y cuántos participan)
   - *Paso 5: Técnicas e Instrumentos* (observación, encuesta, bitácora, escala SUS, etc.)
   - *Paso 6: Procedimiento de recolección de datos* (cómo fue el día de las pruebas)
   - *Paso 7: Técnicas de Análisis de Datos* (estadística descriptiva, Excel)
   - *Paso 8: Aspectos Éticos* (confidencialidad, consentimientos informados)
   - *Guía de figuras*: Inserción de imagen técnica referencial (`Figura 1`).
6. **Resultados esperados**: Con su tabla de matriz autoajustada vinculando objetivos y resultados.
7. **Costo estimado y financiamiento**: Presupuesto anual de recursos en formato autoajustable y notas de autofinanciamiento.
8. **Tabla de contenidos**: Índice de secciones autogenerado mediante el comando `\tableofcontents`.
9. **Cronograma de actividades**: Gantt detallado semanal para 6 meses (24 semanas) que ocupa exactamente el ancho del texto.
10. **Bibliografía**: Listado de referencias formateado en APA 7 impreso en una nueva hoja independiente al final del documento.

## Cómo Usar

### 1. Personalización de la Portada
Edita el archivo `1.-Portada.tex` y personaliza el título del proyecto, línea de investigación, sublínea, tus nombres (AUTOR) y el nombre de tu tutor. Los nombres están preconfigurados con el formato genérico `NOMBRE NOMBRE APELLIDO APELLIDO` como marcador de posición.

### 2. Redacción del Contenido
Sustituye la información del caso de estudio piloto (el sistema de parqueaderos con visión artificial) en el archivo `2.-Contenido.tex` con los datos de tu propia investigación, guiándote por el estilo descriptivo de los ejemplos prácticos.

### 3. Agregar Citas y Referencias
Registra tus referencias en formato BibTeX dentro del archivo `referencias.bib` y cítalas en tu texto usando:
- Cita parentética: `\parencite{ClaveReferencia}`
- Cita narrativa: `\textcite{ClaveReferencia}`

### 4. Compilación del Documento
Para generar el archivo PDF, ejecuta en tu terminal:
```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```
*(O compila usando la extensión **LaTeX Workshop** en VS Code o la plataforma en línea **Overleaf**).*

## Solución de Problemas

| Problema | Solución |
|----------|----------|
| Las tablas se desbordan horizontalmente | Asegúrate de usar `tabular*` con ancho `\textwidth` y establecer un valor pequeño en `\setlength{\tabcolsep}{...}` (por ejemplo, `1.5pt` para tablas anchas). |
| Las tablas ocupan hojas enteras en blanco | Aplica el comando `\singlespacing` justo al inicio del entorno `table`. Esto anula el doble espaciado general de la plantilla en el interior de la tabla. |
| Las referencias no aparecen en el índice (TOC) | La plantilla ya usa `heading=subbibintoc` en `\printbibliography` para que se registre como una sección normal con línea entrecortada. |
| Error de figura no encontrada | Verifica que el archivo de imagen esté guardado en la carpeta `imagenes/` y que la extensión coincida exactamente. |

## Licencia

Esta plantilla se distribuye bajo la licencia **MIT**. Eres libre de usarla, modificarla y compartirla con la comunidad académica.

## Autor de la Plantilla Original
**Ing. José Naranjo, M.Eng.**
- Docente de la Carrera de Ingeniería de Software - PUCEM

*Adaptación realizada para la automatización e integración con la normativa de UIC 2023.*

---
**Última actualización**: Junio 2026
**Estado**: Mantenida y activa para la Carrera de Ingeniería de Software de la PUCEM.
