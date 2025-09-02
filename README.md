El melanoma cutáneo avanzado con mutación en el gen BRAF dispone de dos opciones terapéuticas de primera línea: inmunoterapia e inhibidores BRAF+MEK. Sin embargo, un subgrupo de pacientes no obtiene el beneficio esperado, lo que evidencia la necesidad de encontrar biomarcadores predictivos. 
En este estudio se analizó una cohorte retrospectiva de 30 pacientes mediante Nanostring®, identificándose dos firmas génicas independientes: una asociada a la respuesta a terapia dirigida (11 genes) y otra vinculada a la respuesta a la inmunoterapia (28 genes). 
Estas firmas reflejaron mecanismos biológicos específicos, con perfiles inflamatorios y metabólicos en la terapia dirigida y activación inmunitaria en inmunoterapia. La validación en cohortes externas (RNA-seq y TCGA-SKCM) confirmó su reproducibilidad y relevancia biológica. 
Los resultados sientan las bases para el desarrollo de modelos predictivos basados en expresión génica, que podrían contribuir a una medicina personalizada en melanoma metastásico avanzado.

En este proyecto de fin de Máster en Bioinformática se han seguido varios pasos, que quedan recogidos en diferentes scripts:

1. Control de calidad, normalización de los datos y filtrado de muestras: Nanostring_QC_Norm.Rmd. Para ejecutar este scrip debes tener una carpeta data/Rawdata/ que incluya los archivos .RCC, el archivo NS_xxx.rlf y el archivo NS_xxx.csv (no proporcionados dado que los datos aun no han sido publicados).
   
3. Representación de la expresión génica (mediante heatmap) de las muestras finales tras normalizar: Heatmap_After_SF.Rmd
4. Datos clínicos de las muestras: Caracteristicas_clin.Rmd
5. Análisis de exprsión diferencial: DE_Analysis_Limma.Rmd
6. Validación externa con 2 bases de datos (1 por cada tratamiento) de RNASeq: Validación_BBDD.Rmd
7. Análisis no supervisado: ML.Rmd
