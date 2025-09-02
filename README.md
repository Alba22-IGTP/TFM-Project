
# Biomarcadores Predictivos en Melanoma Metastásico Avanzado

El melanoma cutáneo avanzado con mutación en el gen **BRAF** dispone de dos opciones terapéuticas de primera línea: **inmunoterapia** e **inhibidores BRAF+MEK**. Sin embargo, un subgrupo de pacientes no obtiene el beneficio esperado, lo que evidencia la necesidad de encontrar **biomarcadores predictivos**.  

En este estudio se analizó una cohorte retrospectiva de 30 pacientes mediante **Nanostring®**, identificándose dos **firmas génicas independientes**:  
- **Terapia dirigida (BRAF+MEKi):** 11 genes, asociados a perfiles inflamatorios y metabólicos.  
- **Inmunoterapia (ITH):** 28 genes, vinculados a activación inmunitaria.  

La validación en cohortes externas (**RNA-seq** y **TCGA-SKCM**) confirmó la reproducibilidad y relevancia biológica de estas firmas. Los resultados sientan las bases para el desarrollo de **modelos predictivos basados en expresión génica**, que podrían contribuir a una **medicina personalizada** en melanoma metastásico avanzado.

---

## Estructura del proyecto y scripts

1. **Control de calidad, normalización y filtrado de muestras:**  
   `Nanostring_QC_Norm.Rmd`  
   - Requiere: carpeta `data/Rawdata/` con archivos `.RCC`, `NS_xxx.rlf` y `NS_xxx.csv`  
   - Nota: los datos no se incluyen por razones de privacidad/publicación.

2. **Representación de la expresión génica mediante heatmap:**  
   `Heatmap_After_SF.Rmd`  
   - Incluye un ejemplo de datos clínicos: `clin_data.csv`  
   - Requiere los datos normalizados generados en `Nanostring_QC_Norm.Rmd`.

3. **Datos clínicos de las muestras:**  
   `Caracteristicas_clin.Rmd`  
   - Requiere: `db_completa_log2.csv` generado en `Heatmap_After_SF.Rmd`.

4. **Análisis de expresión diferencial:**  
   `DE_Analysis_Limma.Rmd`  
   - Requiere: `db_completa_log2.csv`.

5. **Validación externa con bases de datos de RNA-seq:**  
   `Validación_BBDD.Rmd`  
   - Requiere:  
     - `GSE91061_BMS038109Sample.hg19KnownGene.fpkm.csv.gz`  
     - `GSE196434_MR_GEO_rawdata.txt.gz`  
     - `db_completa_log2.csv`  

6. **Análisis no supervisado y machine learning:**  
   `ML.Rmd`  
   - Requiere: `db_completa_log2.csv`.

---

## Requisitos

- R ≥ 4.2  
- Paquetes R: `dplyr`, `ggplot2`, `flextable`, `officer`, `ComplexHeatmap`, `limma`, `DESeq2`, entre otros.  

---

## Objetivo

Desarrollar herramientas basadas en expresión génica que permitan predecir la respuesta de pacientes con melanoma metastásico avanzado a **inmunoterapia** o **terapia dirigida**, sentando las bases para un enfoque de **medicina personalizada**.
