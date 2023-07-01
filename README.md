# Diseño de regímenes de tratamiento óptimos en pacientes hipertensos con insuficiencia renal. Un enfoque desde el Aprendizaje por Refuerzo

Código para el Trabajo de Fin de Grado: Diseño de regímenes de tratamiento óptimos en pacientes hipertensos con insuficiencia renal. Un enfoque desde el Aprendizaje por Refuerzo.


El repositorio se organiza según la siguiente estructura:
- Directorio Data: Contiene los archivos CSV de los tres conjuntos de datos empleados para el desrrollo de este proyecto.
  
- Directorio Selecci´on variables y estratificaci´on: Contiene los siguientes archivos:
  • RLM.Rmd para el diseño del modelo de regresi´on lineal m´ultiple y la implementaciónn del método stepwise en dirección backwards. Permite la selección de parámetros más correlacionados con el resultado farmacocin´etico en el s´eptimo d´ıa.
• Estratificacion poblacional.ipynb permite la creaci´on de los subtipos de pacientes
seg´un las variables seleccionadas al ejecutar el archivo anterior
Directorio Modelo AR: contiene los siguientes scripts de Python:
• Extraccion experiencias.py para la extracci´on de la informaci´on de experiencias
a partir de las muestras de interacci´on con el entorno previamente generadas por el
modelo Pop-PBPK.
• Funciones recompensa.py es un script ejecutado internamente por el archivo Extraccion
experiencias.py para implementar el modelo de funci´on de recompensa correspondiente
en la generaci´on de experiencias seg´un c´omo se defina el PDM. Contiene el
dise˜no de las funciones RU y RE.
• RL-T.py para el entrenamiento del modelo de AR implementando el algorimo de
Q-learning seleccionando una configuraci´on de hiperpar´ametros y una funci´on de recompensa
determinadas.
• RL-T tuning.py permite el entrenamiento del modelo de AR implementando la
m´etodolog´ıa de ajuste de hiperpar´ametros del algoritmo de Q-learning y empleando
los dos modelos de funci´on de recompensa comparados en este proyecto.
• RL-P.py permite la extracci´on del r´egimen de dosificaci´on y las trayectorias farmacocin
´eticas de cada paciente siguiendo la pol´ıtica ´optima π∗ a partir de la tabla-Q
31
derivada del entrenamiento y generada por el script RL-T.py.
• RL-P tuning.ipynb permite la extracci´on del r´egimen de dosificaci´on y las trayectorias
de los pacientes para todas las configuraciones de hiperpar´ametros y modelos
de funci´on de recompensas empleados en el contexto de este trabajo.
• RMSE trayectorias completas.py para la creaci´on de todas las trayectorias completas
para 7 d´ıas alamacenadas en los conjuntos de datos y su clasificaci´on basada
en RMSE.
32
