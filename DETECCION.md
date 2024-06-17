
# Detección de Fraude en Proveedores

En este proyecto, se desarrolló un modelo de machine learning para predecir si un proveedor será o no fraudulento. Se utilizó un conjunto de datos que incluye información sobre pacientes, beneficiarios y etiquetas de aprovisionadores.

## Entendimiento de los datos

Para iniciar nuestro trabajo de los datos, detectamos la relación que se encuentra entre los archivos train_beneficiario.csv, train_labels_aprovisionadores.csv, train_pacientes_aprobados.csv y train_pacientes_rechazados.csv para poder hacer las combinaciones que necesitamos.

Unificamos los datos en un archivo para poder detectar los patrones entre cada afiliado y su aprovisionador y de estos poder identificar cuales han sido los que se detectaron como fraudulentos.

## Generación de características

- Análisis de Variables: Se deben analizar todas las variables proporcionadas para comprender su significado y relevancia para el problema
- Selección de Características: Las variables relevantes podrían incluir monto_reembolso, diagnostico_a, diagnostico_b, ..., procedimiento_z, entre otras que se consideren importantes para predecir la propensión al fraude.
- Ingeniería de Características: Se pueden crear nuevas características a partir de las existentes, como la edad a partir de nacimiento, o variables binarias para indicar la presencia de ciertas enfermedades basadas en los diagnósticos.
- Nivel de Granularidad: Podría ser a nivel individual para diagnósticos y procedimientos, o agregado para monto reembolsado y otros.
- Normalización y Escalado: Las variables numéricas como monto_reembolso necesitarían normalización si tienen rangos muy diferentes.
- Codificación de Variables Categóricas: Variables como ciudad, genero, raza, y es_fraudulento (que debería ser transformada en 0 y 1) necesitarían ser codificadas en variables numéricas para el modelo.
- Creación de la Tabla Maestra: La tabla maestra contendría todas las características seleccionadas y transformadas, listas para ser utilizadas en el modelo

## Tipo de aprendizaje y modelo

En este caso utilizamos un modelo de aprendizaje supervisado de clasificación, específicamente el algoritmo Random Forest.
Se utilizo la Tabla maestra que contiene la variable objetivo "Es fraudulento" y se conoce su valor para cada instancia. Así que con este valor entrenamos el modelo para predicciones de ella misma.

Utilizamos el modelo Random Forest, ya que es el algoritmo utilizado para clasificación y regresión basandose en la creación de multiples arboles de decisión que despues combina sus predicciones para mejorar la precisión y evitar lo que es llamado como sobreajuste.

### Razones de uso de Random Forest

- Facilidad de uso: Es facil implementarlo y no requiere hiperparametros de ajuste demasiado complicados.
- Robustez: Es robusto y esto lo hace funcionar muy boien frente a los datos desequilibrados y el ruido que puede producirse en los datos.
- Rendimiento: Suele tener un rendimiento solido en grandes conjuntos de datos, y como ya se menciono, es menos propenso al sobreajuste.

## Definición de la evaluación

Una vez entrenado el modelo, se realizaron predicciones en el conjunto de validación (X_val) y se compararon con las etiquetas reales (y_val). Se utilizó la función classification_report de scikit-learn para obtener métricas como precisión, recall, f1-score y soporte para cada clase (fraude y no fraude). También se calculó la precisión general del modelo utilizando la función accuracy_score.

Al igual que con los datos de entrenamiento, creamos un archivo maesto de de testing llamado test_data.csv, fue este archivo el que enviamos al modelo ya entrenado despues de obtener las caracteristicas anteriores.

## AUC

Tenemos que la AUC (Area Under the Curve) o área bajo la curva indica el rendimiento del modelo. entre mas cercano a 1 mejor el rendimiento.
Aplicando tambien una investigación propia, hecha en el año 2022 sobre ["Definición de porcentaje de accuracy para las variables de acuerdo a modelos de predicción de etiquetas"](https://drive.google.com/file/d/1tQbjipH_SUdTt0bkQZbv2gZmXpa5D1jf/view?usp=sharing) si el accuracy están oscilando entre el 70% y 80%, en estos usan modelos de optimización para mejorar la asertividad y eliminar el número de falsos positivos y falsos negativos que se producen por lo general en los modelos de predicción.

En nuestro caso, encontramos un AUC de 0.8686 indicandonos un alto rendimiento sobre el modelo y que con mas conjuntos de datos podriamos tener un modelo significativamente bueno para la prediccion de fraude en los proveedores.

## Arquitectura de la Red
- Preprocesamiento de Datos: Se combinan y preprocesan los datos de diversas fuentes, se codifican las variables categóricas y se manejan valores nulos.

- Modelo de Machine Learning: Se utiliza un RandomForestClassifier, conocido por su capacidad para manejar datos desequilibrados y características heterogéneas. La arquitectura del modelo no es una red neuronal, sino un conjunto de árboles de decisión que se combinan para hacer predicciones más robustas.

- Entrenamiento y Evaluación: Se entrena el modelo con los datos procesados y se evalúa su rendimiento utilizando métricas estándar. El modelo se guarda para su posterior uso en predicciones.

- Predicciones y Guardado: Se aplican predicciones a nuevos datos y se guardan los resultados para su análisis futuro.

- Este enfoque sigue un pipeline típico de machine learning para detección de fraude, asegurando que los datos se procesen adecuadamente y que el modelo sea robusto y generalizable.
