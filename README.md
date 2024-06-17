# Machine Learning Technical Test

<br>

*¡Bienvenid@!*

<br>

El objetivo de esta prueba técnica es conocer tus capacidades analíticas, ingenieriles y de desarrollo de software para el cargo de Machine Learning Engineer en Leonisa. 

Utiliza las bases de entrenamiento ubicadas en la carpeta `/data/train` para generar un modelo que prediga la propensión al fraude por parte de un aprovisionador (prestador de servicio). Para ello cuentas con 4 bases:
* Labels de aprovisionadores que han sido previamente identificados como fraudulentos o no fraudulentos.
* Información de beneficiarios (pacientes).
* Información de beneficiarios que han sido aceptados para ser atendidos por el aprovisionador.
* Información de beneficiarios que han sido rechazados para ser atendidos por el aprovisionador. 

<br>

> [!TIP]
> Te animamos a que sigas las instrucciones que te presentamos utilizando las librerías, herramientas y tecnologías que te indicamos. Aprovecha tu experiencia, conocimientos y capacidad de investigación para completar la prueba.

<br>

1. Crea un archivo Markdown en el repositorio y describe el proceso a realizar para el desarrollo de un modelo que prediga si un proveedor será o no fraudulento. Te sugerimos abordar de forma concisa los siguientes aspectos:
   1. Entendimiento de la relación entre las diferentes fuente de datos.
   2. Proceso de generación de características y nivel de granularidad de la tabla maestra a partir de la cual se realizará el entrenamiento.
   3. Identificación del tipo de aprendizaje y tipo de modelo más apropiado para el ejercicio.
   4. Definición del proceso de evaluación del modelo.

2. Implementa el proceso descrito utilizando 
**$\color{Aquamarine}{Python}$**
y específicamente utiliza 
**$\color{Aquamarine}{Tensorflow}$** a través de la técnica de 
**$\color{Aquamarine}{Redes\ Neuronales}$** para el desarrollo del modelo. Hazlo en una nueva rama de experimentación.

3. En el mismo archivo Markdown crea nuevas secciones indicando:
   1. Una explicación concisa sobre la arquitectura de la red que definiste y aspectos relevantes de las decisiones de diseño que tuviste en cuenta en el proceso de modelado.
   2. Un análisis de los resultados del modelo indicando mínimo la métrica del 
**$\color{Aquamarine}{AUC}$**.

4. Utiliza las bases de test en la carpeta `/data/test` para aplicar el modelo desarrollado e identificar si los aprovisionadores listados serán o no fraudulentos. Debes actualizar el archivo correspondiente en el repositorio.

5. Con el objetivo de evaluar las métricas de calidad de tu código, utiliza 
**$\color{Aquamarine}{Rancher\ Desktop}$**
para desplegar una imagen de 
**$\color{Aquamarine}{Docker}$**
de la herramienta 
**$\color{Aquamarine}{SonarQube\ (Community\ Edition)}$** 
en un contenedor local. Es una buena opción utilizar un docker-compose para agilizar el proceso.
   
   1. En la consola web de SonarQube crea un proyecto local de forma manual con el nombre `"mle-<nombre_candidato>"` y sigue las instrucciones de la herramienta para ejecutar el análisis de tu proyecto. 
   2. En el mismo archivo Markdown de tu proyecto, crea nuevas secciones mostrando:
      1. Un pantallazo de 
**$\color{Aquamarine}{Rancher\ Desktop}$**
      donde se evidencien las imágenes y otro de los contenedores creados.
      2. Un pantallazo de 
**$\color{Aquamarine}{SonarQube}$** 
      donde se aprecien las métricas de tu código, como el que se muestra en la imagen que está en la carpeta `/img`.

6. Cuando termines la implementación de tu proyecto, crea un PR para que podamos identificar que has terminado tu desarrollo.

<br>

> [!IMPORTANT]
> Agradecemos mucho el tiempo que tomarás para realizar la prueba, esperamos sea de tu agrado para fortalecer tus conocimientos y aprender sobre nuevas herramientas.

<br>

*¡Muchos éxitos!*