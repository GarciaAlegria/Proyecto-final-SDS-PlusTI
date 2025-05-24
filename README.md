# Proyecto Final PlusTi: Priorización de Fraudes Repetidos en Comercios

**Institución:** Universidad del Valle de Guatemala

**Curso:** Security Data Science

**Autor:** Abner Iván García Alegría (21285)

## Resumen

Este proyecto se enfoca en la utilización de técnicas de ciencia de datos para mejorar la detección de fraudes financieros. El objetivo principal es priorizar la identificación de transacciones fraudulentas en comercios que han mostrado una alta recurrencia de incidentes de fraude. Mediante el análisis exploratorio de datos (EDA) y la implementación de modelos de *machine learning*, se buscan patrones distintivos entre transacciones legítimas y fraudulentas, prestando especial atención a la evolución temporal del fraude y su concentración en comercios específicos.
![image](https://github.com/user-attachments/assets/eb33101b-aed2-4042-9595-ff0d9c943bce)


## Metodología

El proyecto siguió un ciclo completo de ciencia de datos:

1.  **Recolección y Comprensión del Dataset:**
    * Se utilizó el conjunto de datos `dataset_feature_engineering.csv`.
    * Contiene atributos como monto (`amount`), categoría (`category`), comerciante (`merchant`), fecha, población de la ciudad (`city_pop`), hora (`hour`), entre otros.
    * La variable objetivo (`is_fraud`) indica si una transacción es fraudulenta (1) o no (0).

2.  **Análisis Exploratorio de Datos (EDA):**
    * Se observó un fuerte desbalance en la variable `is_fraud`.
    * Se analizó la evolución anual del fraude para identificar tendencias.
    * Se identificaron los comercios con mayor número de fraudes por año.
    * Se visualizó que los fraudes tienden a asociarse con montos de transacción más altos.

3.  **Ingeniería de Características:**
    * Se extrajeron componentes temporales (año, mes, hora) de las fechas.
    * Se codificaron variables categóricas como `category` y `merchant` (ej. one-hot encoding).
    * Se normalizaron variables numéricas como `amount` y `city_pop`.

4.  **Manejo del Desbalance de Clases:**
    * Se aplicó la técnica de sobremuestreo SMOTE para generar datos sintéticos de la clase minoritaria (fraudes) y balancear el dataset.

5.  **División del Dataset:**
    * El conjunto de datos se dividió en 80% para entrenamiento y 20% para pruebas.

6.  **Entrenamiento de Modelos:**
    * Se entrenaron y compararon los modelos `Random Forest Classifier` y `XGBoost`.
    * Se utilizaron técnicas de validación cruzada y ajuste de hiperparámetros.

7.  **Evaluación de Modelos:**
    * Se usaron métricas como Accuracy, Precisión, Recall y F1-score, adecuadas para datos desbalanceados.

## Implementación Práctica

* **Lenguaje:** Python.
* **Librerías:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost.
* **Variables Clave:** `amount`, `category`, `merchant`, `age`, `city_pop`, `hour`.

## Resultados Clave

* **Características Importantes:** El monto (`amt`), la categoría (`category`), el año (`amt_year`), la hora (`hour`) y la fecha de nacimiento (`dob`) fueron identificadas como las características más influyentes para predecir el fraude.
* **Métricas del Modelo Base (XGBoost):**
    * AUC ROC: 0.9940 
    * F1 Score: 0.7187 
    * Accuracy: 0.9970 
* **Optimización de Umbral:** Se identificó un umbral óptimo de 0.65, logrando un F1 Score de 0.7216, una Precisión de 0.8057 y un Recall de 0.6534.
* **Modelos:** XGBoost demostró un desempeño general superior en las métricas clave.

## Conclusiones

1.  El análisis histórico por comercio es eficaz para priorizar la detección de fraudes en establecimientos reincidentes.
2.  Los modelos de *machine learning*, especialmente XGBoost, son altamente capaces de predecir transacciones fraudulentas.
3.  El preprocesamiento adecuado y el manejo del desbalance de clases son fundamentales para el éxito del modelo.
4.  La ciencia de datos es una herramienta estratégica para una gestión proactiva y basada en evidencia del riesgo de fraude financiero.

## Recomendaciones

* Implementar el modelo desarrollado en un sistema de monitoreo en tiempo real.
* Actualizar periódicamente el modelo con nuevos datos transaccionales.
* Explorar la inclusión de variables adicionales, como la geolocalización o información del dispositivo.
* Utilizar técnicas de interpretabilidad (como SHAP o LIME) para entender mejor las decisiones del modelo.
