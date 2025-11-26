# El Martillo - OCR y Análisis Digital

## 📰 Sobre el Proyecto

Este proyecto realiza un análisis digital de una página histórica del periódico **"El Martillo"**, publicado en Chiclayo, Perú, el **3 de febrero de 1903** (Edición N° 1609). Utilizando la API de Claude (Anthropic) para OCR (Reconocimiento Óptico de Caracteres), digitalizamos y estructuramos el contenido de esta valiosa pieza histórica.

**Fuente:** [British Library - Endangered Archives Programme (EAP498)](https://eap.bl.uk/collection/EAP498-2-27)

## 📂 Estructura del Repositorio

```
el-martillo-ocr-bianca/
│
├── .gitignore                          # Archivos ignorados por Git
├── requirements.txt                    # Dependencias del proyecto
├── README.md                           # Documentación principal (este archivo)
├── report.md                           # Reporte de análisis e insights
├── el_martillo_ocr_analysis.ipynb     # Notebook con todo el código y análisis
│
└── data/                               # Carpeta de datos
    ├── el_martillo/                    # Subcarpeta de imágenes originales
    │   └── page_01.jpg                 # Página escaneada del periódico (3 Feb 1903)
    │
    ├── el_martillo_structured.csv      # Dataset estructurado (6 entradas)
    └── el_martillo_analysis.png        # Visualizaciones generadas
```

## 🎯 Objetivos

1. Digitalizar una página histórica mediante OCR con Claude API
2. Estructurar el contenido en un dataset CSV analizable
3. Realizar análisis exploratorio del contenido periodístico de 1903
4. Generar visualizaciones informativas sobre la distribución del contenido
5. Documentar insights históricos y desafíos técnicos del proceso

## 🛠️ Tecnologías Utilizadas

- **Python 3.10**
- **Anthropic Claude API (Sonnet 4)** - OCR y análisis de imágenes históricas
- **Pandas** - Manipulación y análisis de datos
- **Matplotlib & Seaborn** - Visualizaciones estadísticas
- **PIL/Pillow** - Procesamiento de imágenes
- **Jupyter Notebook** - Ambiente de desarrollo interactivo

## 🚀 Instalación y Uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/el-martillo-ocr-bianca.git
cd el-martillo-ocr-bianca
```

### 2. Crear environment de Anaconda

```bash
# Crear environment
conda create -n el-martillo python=3.10 -y

# Activar environment
conda activate el-martillo

# Instalar dependencias
conda install -y pandas matplotlib seaborn pillow jupyter notebook ipykernel
pip install anthropic

# Registrar kernel en Jupyter
python -m ipykernel install --user --name=el-martillo --display-name="Python (El Martillo)"
```

### 3. Configurar API Key

Obtén tu API key de [Anthropic Console](https://console.anthropic.com/) y reemplázala en el notebook (Celda 7):

```python
API_KEY = "tu-api-key-de-anthropic"
```

### 4. Ejecutar el notebook

```bash
jupyter notebook
```

Abre `el_martillo_ocr_analysis.ipynb` y ejecuta todas las celdas (Cell → Run All).

## 📊 Dataset Estructurado

El archivo `el_martillo_structured.csv` contiene **6 entradas** con las siguientes columnas:

| Columna | Descripción | Ejemplo |
|---------|-------------|---------|
| `date` | Fecha de publicación | "3 de Febrero de 1903" |
| `issue_number` | Número de edición | "1609" |
| `headline` | Título del artículo/anuncio | "El periodismo departamental" |
| `section` | Sección del periódico | "Editorial", "Noticias Locales", etc. |
| `type` | Tipo de contenido | "artículo", "anuncio", "editorial", "otro" |
| `text_excerpt` | Extracto del texto | Primeras líneas del contenido |

## 📈 Resultados del Análisis

### Estadísticas Generales

- **Total de elementos extraídos:** 6
- **Fecha de publicación:** 3 de Febrero de 1903
- **Número de edición:** 1609
- **Longitud promedio de extractos:** 117 caracteres

### Distribución por Tipo de Contenido

| Tipo | Cantidad | Porcentaje |
|------|----------|------------|
| Artículos | 3 | 50.0% |
| Editorial | 1 | 16.7% |
| Anuncios | 1 | 16.7% |
| Otros | 1 | 16.7% |

### Secciones Identificadas

- Editorial (reflexión sobre periodismo departamental)
- Información Local (periódicos de Lambayeque)
- Noticias Locales (pueblos de la vía férrea)
- Anuncios (máquinas Singer de Rómulo Marchola)
- Información General (publicaciones regionales)

### Insights Principales

1. **Predominancia informativa:** El 50% del contenido son artículos, reflejando la función principal del periódico como medio de información local
2. **Meta-periodismo:** Varios artículos tratan sobre otros periódicos y el desarrollo de la prensa regional
3. **Modernización comercial:** Presencia de anuncios de tecnología importada (máquinas Singer) evidencia conectividad comercial internacional
4. **Conciencia regional:** Fuerte énfasis en el "periodismo departamental" como identidad distinta del centralismo limeño

Ver el reporte completo en [`report.md`](report.md)

## 🔍 Desafíos del OCR

### Principales Obstáculos Técnicos

1. **Problemas de encoding:** Caracteres especiales (á, é, í, ó, ú) aparecen como secuencias extrañas (Ã³, Ã­)
2. **Calidad del documento:** 120 años de antigüedad generan manchas, desgaste y texto ilegible
3. **Tipografía histórica:** Fuentes serif antiguas con tipos móviles e intensidad de tinta variable
4. **Layout complejo:** Múltiples columnas, anuncios intercalados, diferentes tamaños de fuente
5. **Fragmentación:** Algunos artículos con extractos incompletos

### Estrategias Aplicadas

- Claude API Sonnet 4 con capacidades avanzadas de visión
- Prompt estructurado solicitando marcado de secciones ilegibles
- Post-procesamiento del JSON para limpieza de datos
- Validación manual del dataset generado

## 📚 Contexto Histórico

**"El Martillo"** circuló en Chiclayo entre 1903-1919, durante un período crucial:
- Post-Guerra del Pacífico y reconstrucción nacional
- Auge del comercio azucarero en el norte del Perú
- Desarrollo de infraestructura ferroviaria
- Surgimiento de clase media provincial

Esta página documenta:
- El ecosistema mediático diverso de Chiclayo en 1903
- La conectividad comercial internacional (importación de máquinas Singer)
- El debate sobre periodismo regional vs. centralismo limeño
- La infraestructura ferroviaria conectando pueblos de Lambayeque

## 📝 Autor

Bianca Peraltilla
biancaperaltilla@gmail.com

## 📅 Información del Proyecto

- **Fecha de elaboración:** Nov 2025
- **Curso:** Data Science - Python
- **Assignment:** Homework 6 - OCR & Digital Analysis

## 🙏 Agradecimientos

- **British Library** - Endangered Archives Programme (EAP498) por la digitalización del periódico
- **Anthropic** - Por proporcionar acceso a Claude API
- **Fuentes Históricas del Perú** - Por la documentación de archivos históricos lambayecanos

## 📄 Licencia

Este proyecto es parte de un trabajo académico para el curso de Data Science. El contenido del periódico histórico es de dominio público. El código y análisis están disponibles para uso educativo.

## 🔗 Enlaces Relevantes

- [Fuente original - British Library EAP498](https://eap.bl.uk/collection/EAP498-2-27)
- [Fuentes Históricas del Perú](https://fuenteshistoricasdelperu.com/)
- [Anthropic Claude API](https://www.anthropic.com/api)

---

**⚠️ Nota sobre encoding:** Algunos caracteres especiales en el dataset presentan problemas de codificación debido a la antigüedad del documento original. Esto es documentado en el reporte como parte de los desafíos técnicos del OCR en documentos históricos.
