# 🧬 UCEC BIOINFORMÁTICA

> **Replicación Computacional del Análisis Multi-Ómico de CDKN2A como Biomarcador y Diana Terapéutica en el Carcinoma Endometrial de Cuerpo Uterino (UCEC)**

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19026766-blue)](https://doi.org/10.5281/zenodo.19026766)
[![Paper](https://img.shields.io/badge/Paper%20original-Scientific%20Reports%202025-red)](https://doi.org/10.1038/s41598-025-85364-w)
[![TCGA](https://img.shields.io/badge/Data-TCGA%20%7C%20CPTAC%20%7C%20GTEx-blueviolet)](https://xenabrowser.net/)

---

## 👤 Autor

**George Ivanok Muñoz Castillo**  
Universidad Nacional de San Antonio Abad del Cusco  
Escuela Profesional de Ingeniería Informática y de Sistemas — Área de Bioinformática

---

## 📄 Descripción

Este repositorio contiene la **replicación computacional e independiente** del estudio:

> Ma L, Li Y, Wu J, Gao Y. *Bioinformatics approaches to multi-omics analysis of the potential of CDKN2A as a biomarker and therapeutic target for uterine corpus endometrial carcinoma.* **Scientific Reports** (2025) 15:895. https://doi.org/10.1038/s41598-025-85364-w

Se reproducen íntegramente las **6 figuras principales** del artículo original utilizando datos públicos de TCGA, CPTAC y GTEx, accedidos mediante la API oficial de UCSC Xena (`xenaPython`). No se requiere registro ni credenciales para reproducir los análisis.

---

## 🔬 Hallazgos principales replicados

| Figura | Análisis | Resultado clave |
|--------|----------|-----------------|
| **Fig. 1** | Venn + GO + KEGG | 115 genes candidatos → CDKN2A seleccionado |
| **Fig. 2** | Expresión mRNA (TCGA, n=546) | CDKN2A ~7× sobreexpresado en tumor vs normal |
| **Fig. 2E** | Kaplan-Meier supervivencia | HR = 2.9 · log-rank p = 0.0055 |
| **Fig. 3A–D** | Proteómica CPTAC (n=131) | Sobreexpresión proteica desde estadio I |
| **Fig. 3E–F** | Inmunohistoquímica (HPA) | 7/34 tumores tinción fuerte vs 0/17 normal (χ²=22.4, p<0.0001) |
| **Fig. 4** | Rutas de señalización | Asociación con p53/Rb y NRF2 |
| **Fig. 5** | Infiltración inmune (TIMER) | Correlación negativa con CD8+T (rho=−0.321, p=2.43e-08) |
| **Fig. 6** | SCNA + Sensibilidad fármacos | Drug metabolism enriquecido · PD-0332991, Nutlin-3a |

---

## 📁 Estructura del repositorio

```
UCEC-BIOINFOMATICA/
│
├── 📓 CDKN2A_v16_FINAL.ipynb        # Notebook principal con toda la replicación
│
├── 📂 FIGURAS/                       # Figuras generadas en alta resolución
│   ├── Fig1A_Venn.png
│   ├── Fig1B_GO_Enrichment.png
│   ├── Fig1C_KEGG.png
│   ├── Fig2A_Pancancer.png
│   ├── Fig2BCD_UCEC_Expression.png
│   ├── Fig2E_KaplanMeier.png
│   ├── Fig3AD_Proteina_CPTAC.png
│   ├── Fig3E_IHC_Barras.png
│   ├── Fig3F_IHC_Microscopia.png
│   ├── Fig4_Signaling_Pathways.png
│   ├── Fig5A_Immune_Correlation.png
│   ├── Fig5B_KM_Immune_Cells.png
│   ├── Fig5CF_IL2_IFNA1_TNF_TP53.png
│   ├── Fig6A_Volcano_SCNA.png
│   ├── Fig6B_Heatmap.png
│   ├── Fig6C_GSEA_KEGG.png
│   ├── Fig6D_GSEA_DrugMetabolism.png
│   └── Fig6E_Drug_Sensitivity.png
│
├── 📂 DATOS/                         # Datos descargados desde UCSC Xena (caché local)
│   ├── ucec_mrna.parquet
│   ├── ucec_survival.parquet
│   └── tcga_phenotype.parquet
│
├── 📄 Replicacion_CDKN2A_UCEC.pdf   # Paper completo en formato PDF
├── 📄 Replicacion_CDKN2A_UCEC.docx  # Paper completo en formato Word
├── 📄 README.md                      # Este archivo
└── 📄 requirements.txt               # Dependencias Python
```

---

## 🚀 Ejecutar en Google Colab

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19dEMjzgHqKIrEpMX-IuSq2RUXJE01Ard?usp=sharing)

> **La forma más rápida de reproducir este análisis es directamente en Google Colab — sin instalar nada.**

### ⚠️ PASO OBLIGATORIO ANTES DE EJECUTAR EL NOTEBOOK

El notebook requiere **2 archivos de datos** que deben subirse manualmente a Colab antes de correr cualquier celda. Estos archivos **no se descargan automáticamente**.

---

### 📂 Archivos que debes subir a Colab

| Archivo | Descripción |
|---------|-------------|
| `TCGA_survival_data_2.txt` | Datos de supervivencia global (OS) de pacientes UCEC — tiempo de seguimiento y evento de muerte |
| `TCGA_TARGET_phenotype` | Fenotipo clínico de pacientes TCGA — estadio, histología, tipo de muestra |

Ambos archivos están disponibles en la carpeta `DATOS/` de este repositorio.

---

### 🔢 Pasos para ejecutar en Colab

**Paso 1 — Abrir el notebook**

Haz clic en el badge de Colab de arriba o en este enlace:
🔗 https://colab.research.google.com/drive/19dEMjzgHqKIrEpMX-IuSq2RUXJE01Ard?usp=sharing

**Paso 2 — Subir los 2 archivos de datos**

En el panel izquierdo de Colab, haz clic en el ícono de carpeta 📁, luego en el ícono de subida ⬆️ y sube los dos archivos:

```
TCGA_survival_data_2.txt
TCGA_TARGET_phenotype
```

> ⚠️ **IMPORTANTE:** Los archivos deben quedar en la ruta raíz `/content/` de Colab. Si los subes a una subcarpeta el notebook no los encontrará.

```
/content/
├── TCGA_survival_data_2.txt   ✅
└── TCGA_TARGET_phenotype      ✅
```

**Paso 3 — Ejecutar todas las celdas**

Ve a `Runtime` → `Run all` (o `Ctrl + F9`). El notebook instalará las librerías automáticamente en la primera celda.

**Paso 4 — Descargar las figuras**

Al finalizar, las figuras quedan en la carpeta `FIGURAS/`. Descárgalas haciendo clic derecho → `Download`.

> 💡 Los datos de mRNA de TCGA se descargan automáticamente desde UCSC Xena. Solo los 2 archivos de arriba requieren carga manual.

---

## ⚙️ Instalación local (alternativa a Colab)

### 1. Clonar el repositorio

```bash
git clone https://github.com/TU_USUARIO/UCEC-BIOINFOMATICA.git
cd UCEC-BIOINFOMATICA
```

### 2. Instalar dependencias

```bash
pip install -r requirements.txt
```

O directamente:

```bash
pip install pandas numpy matplotlib seaborn scipy lifelines matplotlib-venn scikit-learn xenaPython
```

### 3. Colocar los archivos de datos

Copia los dos archivos en la misma carpeta que el notebook:

```
UCEC-BIOINFOMATICA/
├── CDKN2A_v16_FINAL.ipynb
├── TCGA_survival_data_2.txt   ← aquí
└── TCGA_TARGET_phenotype      ← aquí
```

### 4. Ejecutar el notebook

```bash
jupyter notebook CDKN2A_v16_FINAL.ipynb
```

---

## 📦 Dependencias

```
pandas>=2.1
numpy>=1.26
matplotlib>=3.8
seaborn>=0.13
scipy>=1.11
lifelines>=0.28
matplotlib-venn>=0.11
scikit-learn>=1.3
xenaPython>=0.1.0
jupyter>=1.0
```

---

## 🗄️ Fuentes de datos

Todos los datos son de **acceso público** y se descargan automáticamente:

| Dataset | Plataforma | Descripción | n |
|---------|-----------|-------------|---|
| TCGA-UCEC mRNA | UCSC Xena | Expresión mRNA normalizada (log2 TPM+1) | 546 tumor + 35 normal |
| TCGA-UCEC Supervivencia | UCSC Xena | Tiempo de seguimiento y evento de muerte | 174 tumor |
| TCGA Pan-Cancer Fenotipo | UCSC Xena | Estadio clínico, subtipo histológico, grado | 546 UCEC |
| CPTAC-UCEC Proteómica | UALCAN / PDC | Espectrometría de masas TMT-10 | 100 tumor + 31 normal |
| GTEx-UCEC | GTEx v8 | Expresión en tejido endometrial no tumoral | 35 |
| Human Protein Atlas | HPA (manual) | Imágenes IHC de CDKN2A | 34 tumor + 17 normal |

---

## 📊 Figuras destacadas

### Figura 3F — Inmunohistoquímica (IHC)
Comparación visual de la tinción de CDKN2A entre tejido normal (CAB000093, sin tinción) y tejido tumoral (CAB018232, tinción fuerte marrón intensa).

### Figura 2E — Supervivencia Kaplan-Meier
Pacientes con expresión alta de CDKN2A presentan significativamente peor supervivencia global (**HR = 2.9**, log-rank **p = 0.0055**).

### Figura 5A — Infiltración Inmune
CDKN2A se correlaciona negativamente con linfocitos CD8+T (**rho = −0.321**, **p = 2.43×10⁻⁸**), sugiriendo un rol en la inmunosupresión del microambiente tumoral.

---

## 📝 Citar este trabajo

Si utilizas este código o los análisis de este repositorio, por favor cita:

```bibtex
@misc{munoz2025cdkn2a,
  author       = {Muñoz Castillo, George Ivanok},
  title        = {Replicación Computacional del Análisis Multi-Ómico de CDKN2A
                  como Biomarcador y Diana Terapéutica en UCEC},
  year         = {2025},
  institution  = {Universidad Nacional de San Antonio Abad del Cusco},
  note         = {Replicación de: Ma et al., Scientific Reports (2025) 15:895},
  doi          = {10.5281/zenodo.19026766},
  url          = {https://doi.org/10.5281/zenodo.19026766}
}
```

Y el paper original:

```bibtex
@article{ma2025cdkn2a,
  author  = {Ma, Liang and Li, Yuling and Wu, Jingxian and Gao, Yanfei},
  title   = {Bioinformatics approaches to multi-omics analysis of the potential
             of CDKN2A as a biomarker and therapeutic target for uterine corpus
             endometrial carcinoma},
  journal = {Scientific Reports},
  year    = {2025},
  volume  = {15},
  pages   = {895},
  doi     = {10.1038/s41598-025-85364-w}
}
```

---

## 📜 Licencia

Este proyecto está bajo la licencia **MIT**. Los datos provienen de fuentes públicas (TCGA, GTEx, CPTAC, HPA) y están sujetos a sus propias condiciones de uso.

---

## 🔗 Referencias

- [📄 **Este trabajo en Zenodo — DOI: 10.5281/zenodo.19026766**](https://doi.org/10.5281/zenodo.19026766)
- [Paper original — Ma et al., Scientific Reports 2025](https://doi.org/10.1038/s41598-025-85364-w)
- [UCSC Xena Browser](https://xenabrowser.net/)
- [TCGA — The Cancer Genome Atlas](https://portal.gdc.cancer.gov/)
- [CPTAC — Clinical Proteomic Tumor Analysis Consortium](https://pdc.cancer.gov/)
- [GTEx Project](https://gtexportal.org/)
- [Human Protein Atlas](https://www.proteinatlas.org/)
- [UALCAN](http://ualcan.path.uab.edu/)

---

<p align="center">
  <b>Universidad Nacional de San Antonio Abad del Cusco</b><br>
  Escuela Profesional de Ingeniería Informática y de Sistemas<br>
  Área de Bioinformática · 2025
</p>
