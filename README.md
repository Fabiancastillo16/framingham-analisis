# Framingham Heart Study — Analisis Estadistico
## Tabaquismo intensivo como factor de riesgo de enfermedad coronaria

**Curso**: MCDIA501 - Estadistica Computacional para la Toma de Decisiones  
**Magister**: Ciencia de Datos e Inteligencia Artificial - Universidad Andres Bello  
**Evaluacion**: Formativa 1 | Fase 2

---

## Estructura del proyecto

```
Framingham-analisis/
|
+-- formativa-1-eda-inferencia/
|   |
|   +-- data/
|   |   +-- raw/
|   |       +-- framingham.csv          <- dataset original (descargar de Kaggle)
|   |
|   +-- informe/
|   |   +-- informe_tabaquismo_chd.tex  <- fuente LaTeX del informe
|   |   +-- informe_tabaquismo_chd.pdf  <- PDF compilado (entregar en Canvas)
|   |   +-- figs/                       <- generadas automaticamente al correr el notebook
|   |       +-- fig1_dist_cigs.pdf
|   |       +-- fig2_prevalencia_categoricas.pdf
|   |       +-- fig3_sysBP_grupos.pdf
|   |       +-- fig4_IC_CHD.pdf
|   |       +-- fig5_contingencia.pdf
|   |       +-- fig6_scatter_cigs_sysbp.pdf
|   |
|   +-- analisis_tabaquismo_chd.ipynb   <- notebook principal
|
+-- README.md                           <- este archivo
+-- requirements.txt                    <- dependencias Python
```

---

## Instalacion de dependencias

Ejecuta **una sola vez** desde la raiz del proyecto (`Framingham-analisis/`):

```bash
pip install -r requirements.txt
```

Esto instala: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `jupyter`, `ipykernel`.

---

## Como ejecutar el analisis

1. Descarga el dataset desde Kaggle y coloca el archivo en:
   ```
   formativa-1-eda-inferencia/data/raw/framingham.csv
   ```
   Fuente: https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression

2. Abre el notebook desde la carpeta `formativa-1-eda-inferencia/`:
   ```bash
   cd formativa-1-eda-inferencia
   jupyter notebook analisis_tabaquismo_chd.ipynb
   ```
   O abrir directamente en VS Code.

3. Ejecuta todas las celdas en orden: `Cell -> Run All`

   Las figuras se guardan automaticamente en `informe/figs/`.

---

## Como compilar el informe LaTeX

Desde la carpeta `informe/`:

```bash
cd formativa-1-eda-inferencia/informe
pdflatex informe_tabaquismo_chd.tex
pdflatex informe_tabaquismo_chd.tex
pdflatex informe_tabaquismo_chd.tex
```

> Se compila 3 veces para que el indice y las referencias cruzadas queden correctos.

**Nota**: Las figuras deben estar generadas antes de compilar el PDF.  
Si quieres incluir el logo UNAB, coloca `logo_unab.png` en la carpeta `informe/`
y descomenta la linea correspondiente en el `.tex`.

---

## Descripcion del estudio

| Campo | Detalle |
|---|---|
| **Pregunta central** | Es el tabaquismo intensivo (>=20 cig/dia) un factor de riesgo significativo de CHD a 10 anyos? |
| **Dataset** | Framingham Heart Study, 4,238 pacientes, 16 variables |
| **Variable objetivo** | TenYearCHD (enfermedad coronaria a 10 anyos) |
| **Variable exposicion** | heavy_smoker (consumo >= 20 cigarrillos/dia) |
| **Metodos aplicados** | Estadistica descriptiva, IC 95%, Chi-cuadrado, t de dos muestras, t una muestra |

### Resultados principales

| Hallazgo | Resultado |
|---|---|
| Prevalencia CHD — No fumadores | 14.5% IC95%=[13.0%, 16.0%] |
| Prevalencia CHD — Fumadores intensivos | 18.2% IC95%=[16.0%, 20.4%] |
| Prueba chi-cuadrado | chi2=11.23, p=0.0008 -> SE RECHAZA H0 |
| Odds Ratio | OR=1.36 (intensivos tienen 36% mas odds de CHD) |

---

## Criterios de rubrica cubiertos

| Criterio | Seccion notebook | Seccion informe |
|---|---|---|
| ID1.2 Estadistica descriptiva (15 pts) | Seccion 2 | Seccion 2 |
| ID1.3 Intervalos de confianza (15 pts) | Seccion 3 | Seccion 3 |
| ID1.4 Pruebas de hipotesis (15 pts) | Seccion 4 | Seccion 4 |
| Documentacion (15 pts) | Celda 1 + comentarios | Seccion 5 |
| Interpretacion (15 pts) | Seccion 5 | Seccion 6 |
| Presentacion formal (15 pts) | — | Seccion 7 |
| Participacion foro (9 pts) | — | Entrega separada en Canvas |

---

## Integrantes

- [Nombre Integrante 1]
- [Nombre Integrante 2]  
- [Nombre Integrante 3]

**Docente**: [Nombre del docente]  
**Fecha**: Junio 2026