# AquaGest - Trazabilidad y Control de Cambios

Repositorio académico correspondiente al **Taller de Diseño de la Matriz de Trazabilidad del ERS y Simulación de un Proceso de Cambio de Requisitos (Change Control Board)**, aplicado al proyecto:

> **AquaGest - Sistema para la Gestión Inteligente de una Camaronera**

## Información académica

| Campo | Información |
|---|---|
| Universidad | Universidad Técnica Estatal de Quevedo |
| Carrera | Ingeniería de Software |
| Asignatura | Ingeniería de Requisitos (ISR-401) |
| Paralelo | Cuarto semestre "A" |
| Docente | Ing. Guerrero Ulloa Gleiston Cicerón |
| Actividad | Taller de trazabilidad y Change Control Board |
| Fecha | 27 de julio de 2026 |

## Integrantes

| Integrante | Responsabilidades en el CCB |
|---|---|
| Castro Bajaña Ariel Omar | Presidente del CCB y analista de requisitos |
| Mera Arias Erick Jhair | Gestor de configuración y arquitecto/líder técnico |
| Sánchez Centeno Roselyn Andreína | Responsable de calidad y representante del cliente/usuario |

## Descripción

AquaGest es una propuesta de sistema orientada a apoyar la gestión operativa de una camaronera mediante el registro, seguimiento y análisis de información relacionada con estanques, siembras, calidad del agua, alimentación, sanidad, personal, inventario, mantenimiento, cosechas y reportes.

En esta entrega se establece la trazabilidad bidireccional entre las evidencias obtenidas durante la elicitación, los requisitos del sistema, los casos de uso y los casos de prueba. Además, se simula un proceso formal de control de cambios mediante la solicitud `RFC-01` y la participación de un **Change Control Board (CCB)**.

## Objetivo del repositorio

Documentar y mantener organizados los artefactos utilizados para:

- Definir la línea base del ERS de AquaGest.
- Identificar los elementos trazables del proyecto.
- Relacionar evidencias, requisitos, casos de uso y pruebas.
- Verificar la cobertura y detectar elementos huérfanos.
- Analizar el impacto de una solicitud de cambio.
- Registrar la decisión del CCB.
- Actualizar la línea base y conservar evidencia del cambio.
- Presentar la contribución individual de cada integrante.

## Resumen de la trazabilidad

| Elemento | Identificadores | Cantidad |
|---|---|---:|
| Evidencias de elicitación | `EV-01` a `EV-04` | 4 |
| Requisitos funcionales | `RF-01` a `RF-25` | 25 |
| Requisitos no funcionales | `RNF-01` a `RNF-07` | 7 |
| Casos de uso | `CU-01` a `CU-16` | 16 |
| Casos de prueba iniciales | `CP-01` a `CP-32` | 32 |
| Caso de prueba incorporado por la RFC | `CP-33` | 1 |
| Solicitud de cambio | `RFC-01` | 1 |

La matriz permite seguir cada elemento en ambos sentidos:

```text
Evidencia <-> Requisito <-> Caso de uso <-> Caso de prueba
```

## Solicitud de cambio analizada

La solicitud `RFC-01` propone incorporar el envío de alertas críticas mediante WhatsApp, además de su visualización en el panel del sistema.

El análisis considera principalmente:

- `RF-10`: alerta por parámetros del agua fuera de rango.
- `RF-16`: alerta de mortalidad anormal.
- `RNF-01`: eficiencia de desempeño.
- `RNF-02`: disponibilidad.
- `RNF-05`: tolerancia a fallos y funcionamiento sin conexión.
- `CU-02`: registrar parámetros del agua.
- `CU-11`: registrar incidente sanitario.
- `CP-10`, `CP-16` y el nuevo `CP-33`.

## Documentos de la entrega

| Archivo | Contenido |
|---|---|
| `informe_taller_trazabilidad.pdf` | Informe grupal integrado |
| `parte1_castro.pdf` | Identificación de ítems, enlaces de traza, RFC y decisión del CCB |
| `parte2_mera.pdf` | Línea base, matriz completa, impacto técnico y cierre |
| `parte3_sanchez.pdf` | Cobertura, elementos huérfanos, calidad e impacto para el usuario |
| `README.md` | Descripción y guía general del repositorio |

## Estructura recomendada

```text
IR_Semana13/
├── README.md
├── informe_grupal/
│   ├── main.tex
│   ├── main.pdf
│   ├── referencias.bib
│   └── figuras/
├── partes_individuales/
│   ├── parte1_castro.pdf
│   ├── parte2_mera.pdf
│   └── parte3_sanchez.pdf
└── evidencias/
    ├── matriz_trazabilidad/
    ├── rfc/
    ├── acta_ccb/
    └── commits/
```

## Línea base

| Campo | Valor |
|---|---|
| Documento base | ERS de AquaGest - Entrega PFC2 (1B) |
| Versión inicial | `v2.0` |
| Fecha de la línea base | 27 de junio de 2026 |
| Cambio evaluado | `RFC-01` |

El hash del commit utilizado como línea base y el commit de cierre deben registrarse en el informe con sus valores reales. Para consultarlos:

```bash
git log --oneline
```

Para obtener únicamente el hash del commit actual:

```bash
git rev-parse --short HEAD
```

## Compilación del informe

### Requisitos

- TeX Live, MiKTeX u otra distribución compatible con LaTeX.
- Compilador `pdfLaTeX`.
- BibTeX para procesar las referencias.
- `latexmk` para la compilación automática.

### Compilación automática

Desde la carpeta `informe_grupal`:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

### Compilación manual

```bash
pdflatex -interaction=nonstopmode main.tex
bibtex main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

Este orden actualiza correctamente las citas, referencias, tablas, índice e hipervínculos.

### Compilación en Overleaf

1. Crear un proyecto nuevo en Overleaf.
2. Cargar el contenido completo de la carpeta `informe_grupal`.
3. Seleccionar `main.tex` como documento principal.
4. Elegir `pdfLaTeX` como compilador.
5. Presionar **Recompile**.

## Clonar el repositorio

```bash
git clone https://github.com/Erick-Mera/IR_Semana13.git
cd IR_Semana13
```

## Lista de verificación

- [ ] El informe grupal se encuentra en formato PDF.
- [ ] Se incluyeron las tres partes individuales.
- [ ] El informe puede reproducirse desde `main.tex`.
- [ ] La línea base contiene el hash real del commit.
- [ ] La matriz incluye evidencias, requisitos, casos de uso y pruebas.
- [ ] La `RFC-01` identifica los requisitos afectados.
- [ ] El análisis de impacto se deriva de la matriz.
- [ ] El acta del CCB contiene la decisión y su justificación.
- [ ] Se registró la nueva línea base.
- [ ] El repositorio contiene evidencia del commit de cierre.
- [ ] No quedan marcadores como `[COMMIT-HASH-A-COMPLETAR]`.

## Repositorio

https://github.com/Erick-Mera/IR_Semana13

## Referencias

[1] ISO/IEC/IEEE, *ISO/IEC/IEEE 29148:2018: Systems and software engineering - Life cycle processes - Requirements engineering*, 2018. https://www.iso.org/standard/72089.html

[2] IEEE Computer Society, *Guide to the Software Engineering Body of Knowledge, Version 4.0a*, 2024. https://www.computer.org/education/bodies-of-knowledge/software-engineering/v4

---

**Trabajo académico desarrollado por Castro Bajaña Ariel Omar, Mera Arias Erick Jhair y Sánchez Centeno Roselyn Andreína.**
