# Diseño de regímenes de tratamiento óptimos en pacientes hipertensos con insuficiencia renal. Un enfoque desde el Aprendizaje por Refuerzo

Código para el Trabajo de Fin de Grado: Diseño de regímenes de tratamiento óptimos en pacientes hipertensos con insuficiencia renal. Un enfoque desde el Aprendizaje por Refuerzo.


El repositorio se organiza según la siguiente estructura:
- Directorio Data: Contiene los archivos CSV de los tres conjuntos de datos empleados para el desrrollo de este proyecto.
  
- Directorio Selección variables y estratificación: Contiene los siguientes archivos:
  
  -  RLM.Rmd para el diseño del modelo de regresi´on lineal m´ultiple y la implementaciónn del método stepwise en dirección backwards.   Permite la selección de parámetros más correlacionados con el resultado farmacocinético en el séptimo día.
    
  -  Estratificacion_poblacional.ipynb permite la creaci´on de los subtipos de pacientes según las variables seleccionadas al ejecutar el archivo anterior

- Directorio Modelo AR: contiene los siguientes scripts de Python:

  - Extraccion_experiencias.py para la extracción de la información de experiencias a partir de las muestras de interacción con el entorno previamente generadas por el modelo Pop-PBPK.
    
  - Funciones_recompensa.py es un script ejecutado internamente por el archivo Extraccion_experiencias.py para implementar el modelo de función de recompensa correspondiente en la generación de experiencias según cómo se defina el PDM. Contiene el diseño de las funciones RU y RE.
    
  - RL-T.py para el entrenamiento del modelo de AR implementando el algorimo de Q-learning seleccionando una configuración de hiperpar´ametros y una función de recompensa determinadas.
    
  - RL-T tuning.py permite el entrenamiento del modelo de AR implementando la metodología de ajuste de hiperparámetros del algoritmo de Q-learning y empleando los dos modelos de función de recompensa comparados en este proyecto.
    
  - RL-P.py permite la extracci´on del régimen de dosificación y las trayectorias farmacocinéticas de cada paciente siguiendo la política óptima π∗ a partir de la tabla-Q derivada del entrenamiento y generada por el script RL-T.py.
    
  - RL-P tuning.ipynb permite la extracción del régimen de dosificación y las trayectorias de los pacientes para todas las configuraciones de hiperparámetros y modelos de función de recompensas empleados en el contexto de este trabajo.
    
  - RMSE trayectorias completas.py para la creación de todas las trayectorias completas para 7 días alamacenadas en los conjuntos de datos y su clasificaci´on basada en RMSE.
