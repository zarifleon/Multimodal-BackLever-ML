# Cuantificación Multimodal de Calidad y Costo en Isométricos de Alta Intensidad: Back Lever

Sistema de análisis multimodal para cuantificar calidad técnica y costo fisiológico
del Back Lever en anillas, combinando visión por computadora con señales fisiológicas
de alta resolución. Estudio N=1, 12 sesiones, 4 series por sesión, con incremento
de frecuencia de entrenamiento de 1→3 sesiones/semana.

## Requisitos

* Python 3.12

## Configuración

Instala [uv](https://docs.astral.sh/uv/getting-started/installation/):

```bash
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Sincroniza el entorno desde el lockfile:

```bash
uv sync
```

## Ejecución

Abre el notebook principal:

```bash
uv run jupyter lab Multimodal-Backlever-ML.ipynb
```

Las secciones 0–1 cubren configuración de entorno y carga de datos. La sección 2
contiene el EDA de video y señales Polar H10. La sección 3 implementa el
preprocesamiento de video (score técnico por frame) y extracción de features
fisiológicos. La sección 4 contiene el modelado (GPR, score compuesto, correlaciones).

## Estructura del proyecto

├── Multimodal-Backlever-ML.ipynb   # Notebook principal
├── pyproject.toml
├── uv.lock
├── .python-version
├── data/                           # Videos y datos crudos de Polar H10
├── prep/                           
└── outputs/                        # Figuras, métricas y resultados del modelado
