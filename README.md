# aprendizaje_automatico_proyecto
Autoras

·Marta González Arroyo (marta.gonzalez@cunef.edu)

·Cristina Morcillo Ruiz (cristina.morcillo@cunef.edu)

·María Barbero Jiménez (maria.barbero@cunef.edu)

Link al repositorio:
https://github.com/mariabarberoc/aprendizaje_automatico_proyecto.git



## 1. Planteamiento del problema de negocio

En la industria músical actual Spotify y Youtube se han convertido en las principales plataformas indicadoras de éxito de una canción. Las discográficas o los propios artistas, publican canciones pero no siempre está claro qué características musicales conectan mejor con el público.

El objetivo principal de este proyecto busca desarrollar un modelo de Machine Learning capaz de predecir el nivel de éxito de una cancion a partir de sus características musicales y métricas de difusión.

Enfocado en predecir qué tipo de canciones funcionan mejor para ayudar a artistas que desean orientar su musica a lo que mejor conecta y alcanzar un mayor número de oyentes.

Además ayudar a discográficas a priorizar qué tipo de canciones promocionar e invertir en aquellas con mayor probabilidad de éxito,
Comprender el comportamiento del público según el tipo de canción, sus atributos sonoros o la interaccion en dos grandes plataformas. 
 
Para ello se analizan datos de grandes platafromas como Spotify y Youtube, considerando metricas de popularidad y variables que miden la sonoridad y composicion.

El valor de este proyecto reside en que permite apoyar la toma de decisiones en fases tempranas del proceso creativo y de promoción musical, centrándose en características musicales y variables estructuradas, y evitando el uso de información posterior que podría introducir filtraciones de datos.

Preguntas a resolver:

•⁠  ⁠¿Qué tipo de canciones conviene priorizar e invertir por parte de una discográfica?

•⁠  ⁠¿Qué características musicales se asocian a las canciones más exitosas?

•⁠  ⁠¿Se puede predecir el éxito de una canción antes de su lanzamiento?

•⁠  ⁠¿Se pueden identificar nuevos talentos o nichos musicales con potencial de éxito?



## 2. Planteamiento científico

Tipo de aprendizaje:
Se plantea un problema de aprendizaje supervisado, con un tarjet definido que permite medir de manera cuantitativa las el éxito en las canciones

Cada observación del dataset corresponde a una canción individual, caracterizada por sus atributos musicales y variables asociadas a su difusión en las plataformas.


Variable objetivo / Target:
La variable objetivo seleccionada es Stream, que representa el número de reproducciones que una canción obtiene en Spotify.
Este valor actúa como indicador principal del éxito de una canción dentro de la plataforma.

Vectores de atributos / Features:
Se seleccionarán aquellas variables que reflejan la composición musical como la disfusion y engagement 

Danceability

Energy

Valence

Tempo

Acousticness

Speechiness

Instrumentalness

Liveness

Loudness

Key

Duration_ms

Official_video 

Licensed


Restricciones y filtros:
Las variables utilizadas como atributos se limitan a aquellas que están disponibles de forma previa o independiente al rendimiento posterior de la canción. En particular, se excluyen métricas de interacción en YouTube que solo se conocen tras la publicación, con el fin de evitar filtraciones de información y mantener la coherencia con el objetivo de predicción.


Objetivo científico:
Entrenar un modelo capaz de relacionar las características musicales y la difusion digital con el éxito de las canciones, identificando patrones que permitan orientar decisiones estratégias en producción y promocion musical. Así como detectando talentos emergentes o nichos musicales con potencial.



## 3. Dataset

Para este proyecto, utilizamos el dataset "Spotify and Youtube" encontrado en Kaagle.

Fuente del dataset:

https://www.kaggle.com/datasets/salvatorerastelli/spotify-and-youtube


Descripcion del dataset:

El conjunto de datos combina información de canciones en dos de las platafromas más usadas Spotify y Youtube, con algunas características de audio como la energia, valance, entre otras, así como métricas para la popularidad que nos permiten predecir la popularidad o analizar las tendencias musicale.

Contiene un total de 27 variables:

·Unnamed: 0: columna que actúa como índice o identificador interno de dataset. Numera las filas del archivo original para mantener el origen de los datos.

·Track: nombre de la canción, tal como aparece en Spotify

·Artist: nombre del artista de cada canción.

·Url_Spotify: enlace directo a la cancion en la plataforma.

·Album: normbre del álbum al que pertenece la camción.

·Uri: identificador único de Spotify utilizado para acceder a la canción 

·Danceability: esta variable cuantifica qué tan adecueda es una camcion para bailar, combina elementos musicales como el tempo, beat o la regularidad. En un rango de 0.0 a 1.0, indica que cancion es poco bailable o muy bailable a medida que se aproxima a 1.0

·Energy: en el rango de 0.0 a 1.0, representa la intesidad y actividad de la canción. Canciones cercanas a 1.0 serán las más rápidas, ruidosas y enérginas, mientras que las cercanas a 0.0 son las calmadas o suaves.
    
·Key: tonalidad musical de la cancion,codificada originalmente como un valor numérico, donde cada numero representa una tonalidad musical concreta

0 = C

1 = C# / Db
        
2 = D

3 = D# / Eb

4 = E

5 = F

6 = F# / Gb

7 = G

8 = G# / Ab

9 = A

10 = A# / Bb

11 = B

-1 = no se detecta ninguna tonalidad


·Loudness: volumen global promedio de la cancion en decibelios(dB), los valores típicos se recogen entre -60dB y 0dB, los valores más altos indican mayor volumen percibido.

·Speechiness: detecta la presencia de palabras habladas en la cancion. Valores mayores a 0.66 presentan contenido principalmente hablado, como pueden ser audiolibros, valores entre 0.33-0.66 estan mezclados de voz y música, menores de 0.33 el contenido será principalmente música.

·Acousticness: indica la probabilidad de que la canción sea acustica, 0.0 identificara baja confianza y 1.0 alta confianza de que la canción sea acustica.

·Instrumentalmess: predice si la cancion carece de vocales, cuanto mas cercano a 1.0 sea el valor, mayor probabilidad de que la cancion sea instrumental.

·Livenes: detecta la presencia de audiencia en la grabacion, los valores mayores a 0.8 seran aquellos en los que habrá mayor probabilidad de que la grabación sea en directo. 

·Valence: mide en valores en el rango de 0.0 a 1.0 la positividad de la cancion, 0.0 para las canciones más tristes y 1.0 a las más alegres o positivas.

·Tempo: velocidad o ritmo promedio de la cancion cuantificado en beats por minuto.

·Duration_ms: duración de la cancion en milisegundos.

·Stream: representa el número de reproducciones en Spotify.

·URl_youtube: enlace del video musical en Youtube de la cancion.

·Title: título del videoclip en la plataforma Youtube.

·Channel: nombre del canal que sube el video a la plataforma.

·Views: número de visitas del video de Youtube.

·Likes: número de likes del video de Youtube.

·Comments: número de comentarios del video de Youtube.

·Description: descripción del video en Youtube

·Licensed: esta variable indica si el contenido esta protegido con derechos de autor y pertenece a un partner oficial de la plataforma, en este caso podemos ver

True: contenido licenciado y su distribución controlada por un socio de Youtube

False: contenido no licenciado 

·Oficial_video: indica si el video es el video oficial de la cancion 

True: es el video oficial subido por el artista o la disográfica

False: indica si el video no es oficial, como puede ser un cover o combina varias canciones


Este diccionario de variables permite comprender la naturaleza de los datos disponibles y sirve como base para las decisiones de limpieza, selección de atributos y modelado realizadas en las siguientes etapas del proyecto.


## 4. Diseño experimental

Para garantizar una evaluación realista y evitar filtraciones de información o data leakage, se separa el dataset en dos conjuntos independientes:

- Train (spotify_limpio_train.csv): conjunto de datos resultante tras el proceso de limpieza y análisis exploratorio, utilizado posteriormente para el feature engineering, el entrenamiento de modelos y la selección de hiperparámetros.


- Test (spotify_test.csv): reservado exclusivamente para la evaluación final del modelo.

La partición se realiza mediante una división aleatoria 80/20 `test_size = 0.2` con `random_state = 42`, de manera que los resultados sean reproducibles.

La limpieza y el análisis exploratorio se realizan inicialmente sobre el conjunto de entrenamiento, y una vez finalizados, se exportan los conjuntos definitivos de train y test para su uso en las siguientes etapas del proyecto.

Utilizamos la validación cruzada sobre el conjunto de entrenamiento de esta forma podemos comparar modelos baseline y algoritmos candidatos, seleccionar variables/transformaciones, y ajustar hiperparámetros.

Sin olvidar que el conjunto de test permanece completamente aislado hasta la fase final.

Se utiliza un 20% de los datos como conjunto de test para contar con suficientes ejemplos no vistos que permitan evaluar el rendimiento final del modelo. Al mismo tiempo, esta proporción deja la mayor parte de los datos para entrenamiento, lo que resulta importante en un problema de regresión con una variable objetivo (Stream) muy variable.



## 5. Análisis exploratorio de datos (EDA) y limpieza

Antes de realizar el análisis exploratorio, se eliminaron las observaciones con valores nulos en la variable objetivo `Stream`, ya que no es posible entrenar modelos de regresión sin un target definido. Tras este paso, el dataset se dividió en conjuntos de entrenamiento y test.

El EDA y la limpieza se realizaron únicamente sobre el conjunto de entrenamiento, con el fin de evitar filtraciones de información. En esta fase se analizaron los tipos de variables, la presencia de valores faltantes y las distribuciones de las variables numéricas para comprobar la coherencia de los datos.

Durante este análisis eliminamos columnas no relevantes para el modelado, como descripciones o URLs de vídeos. También se detectamos valores erróneos en variables como Loudness, que fueron eliminados. La variable Instrumentalness presentaba escasa variabilidad y se descartó, mientras que Key y Tempo fueron transformadas para facilitar su interpretación, manteniendo representaciones numéricas adecuadas para el modelado.

Posteriormente, se analizó la relación entre las variables así como la correlación, lo que permitió plantear hipótesis iniciales sobre qué características musicales podrían estar asociadas a un mayor número de reproducciones.

Todas las decisiones y criterios definidos durante el EDA se establecieron únicamente a partir del conjunto de entrenamiento. Dado que se trata de un problema de regresión con una variable objetivo muy variable, se seleccionó el RMSE como métrica principal de evaluación.



## 6. Baseline model


Como primer paso en la fase de modelado, se entrenó un modelo baseline con el objetivo de contar con una referencia inicial de rendimiento. Este modelo permite evaluar si las transformaciones posteriores y el uso de algoritmos más complejos aportan una mejora real.

Para entrenar el modelo baseline, utilizamos el conjunto de entrenamiento limpio (spotify_limpio_train.csv) y se eliminaron las variables de tipo string, ya que no pueden ser utilizadas directamente por los algoritmos de regresión empleados. Como algoritmo base se utilizó un modelo de regresión lineal, por tratarse de una opción simple y razonable para establecer una referencia inicial.


El modelo se evaluó mediante validación cruzada de 5 folds utilizando el RMSE como métrica de evaluación porque penaliza en mayor medida los errores grandes, lo que resulta especialmente relevante en este problema, donde el objetivo es evitar desviaciones importantes en la predicción del número de reproducciones.

Los resultados obtenidos mostraron un error elevado, en parte debido a la alta magnitud y variabilidad de la variable objetivo Stream. 
Aun así, este modelo sirve como referencia inicial para comparar el efecto de las transformaciones y de modelos más complejos en las siguientes etapas.



## 7. Feature engineering

El proceso de feature engineering se realizó de forma iterativa y siempre sobre el conjunto de entrenamiento, utilizando validación cruzada para evaluar cada cambio y sin hacer uso del conjunto de test en ningún momento.

En primer lugar, se probó una transformación logarítmica sobre la variable objetivo `Stream`. Debido a la alta dispersión y magnitud de los valores de reproducciones. Al aplicar el logaritmo, se obtuvo una distribución más equilibrada y una mejora en el rendimiento del modelo baseline, por lo que se decidió mantener esta transformación.

Posteriormente, se evaluó la normalización de algunas variables numéricas con escalas muy diferentes, como Tempo, Loudness y Duration_ms. Para comprobar su utilidad, se entrenó nuevamente el modelo baseline utilizando estas variables normalizadas. Sin embargo, los resultados no mostraron una mejora en el RMSE, por lo que se decidió no aplicar la normalización.

A continuación, se analizó la relevancia de las variables de forma individual y por pares, eliminándolas de manera iterativa y evaluando en cada caso el rendimiento del modelo baseline mediante validación cruzada. 

Este análisis permite comprobar que la eliminación de variables no conducía a mejoras en el RMSE. En algunos casos, la exclusión de determinadas variables incluso empeoraba el rendimiento del modelo.

Por tanto, concluimos que la transformación más relevante en esta fase fue la aplicación del logaritmo sobre la variable objetivo, y que no resultaba conveniente eliminar variables adicionales. 



## 8. Algoritmos cantidatos

Una vez definido el conjunto final de variables tras la fase de feature engineering, probamos distintos algoritmos de regresión con el objetivo de comparar su rendimiento y seleccionar el más adecuado para el problema planteado.

Previamente al entrenamiento, se eliminaron las variables de tipo string, ya que no pueden ser utilizadas directamente por los modelos. Además, se utilizó la variable objetivo transformada mediante logaritmo, tal y como se concluyó en la fase anterior.

Además del modelo baseline, se entrenaron los siguientes algoritmos:
- Random Forest Regressor  
- Gradient Boosting Regressor  
- XGBoost Regressor  

Todos los modelos se entrenan utilizando el conjunto de entrenamiento y se evaluan mediante validación cruzada de 5 folds. Para la comparación utilizamos distintas métricas de regresión, entre ellas RMSE, MAE, MAPE y R², lo que permitió analizar el rendimiento de los modelos desde distintos puntos de vista.

A partir de los resultados obtenidos, se observó que el modelo de Random Forest presentaba el mejor rendimiento global, mostrando los valores más bajos en RMSE, MAE y MAPE, así como un valor mayor de R². 

De esta forma, seleccionamos Random Forest como algoritmo final para continuar con la fase de ajuste de hiperparámetros.


## 9. Selección de hiperparámetros

Tras seleccionar Random Forest como el algoritmo con mejor rendimiento, procedemos al ajuste de sus hiperparámetros con el objetivo de optimizar el modelo.

El ajuste de hiperparámetros empleamos dos enfoques distintos: GridSearchCV y RandomizedSearchCV.

Ambos métodos condujeron a resultados muy similares, concluyendo como configuración óptima 

- n_estimators=500 

- max_depth=None 

- min_samples_split=2

La coincidencia entre ambos métodos refuerza la robustez de la selección realizada.

Durante todo este proceso no se utilizó el conjunto de test, que se mantuvo completamente aislado para la evaluación final del modelo.



## 10. Modelo final y evaluación 

Una vez seleccionado el algoritmo y los hiperparámetros definitivos, se entrenó el modelo Random forest final utilizando todo el conjunto de entrenamiento `spotify_limpio_train.csv`, con el objetivo de aprovechar la mayor cantidad posible de datos.

El modelo se utilizó para predecir los valores del conjunto de test `X_test`, que no había sido utilizado en ninguna de las etapas previas del proyecto.

Dado que durante el modelado se trabajó con la variable objetivo transformada mediante logaritmo, las predicciones obtenidas se transformaron de nuevo a la escala original para poder interpretar correctamente los resultados en términos de número de reproducciones.

La evaluación del modelo se realizó exclusivamente sobre el conjunto de test `spotify_test.csv`, utilizando el RMSE como métrica principal de evaluación, ya que penaliza en mayor medida los errores grandes y resulta más adecuada dado el alto rango y la dispersión de la variable objetivo.

Los resultados obtenidos proporcionan una estimación realista de la capacidad del modelo para predecir el número de reproducciones de canciones no vistas.

Además del modelado, se utilizamos distintas visualizaciones gráficas sirvieron como una herramienta clave para responder a las preguntas de negocio planteadas:

**¿Qué tipo de canciones conviene priorizar e invertir por parte de una discográfica?**  
Los resultados muestan que conviene priorizar canciones con un perfil musical comercial y equilibrado. En general, las canciones más exitosas presentan una mayor intensidad sonora, baja acousticness y baja speechiness, así como una duración moderada. Este tipo de producciones parecen tener una mayor aceptación por parte del público.

**¿Qué características musicales se asocian a las canciones más exitosas?**  
Las canciones con mayor número de reproducciones tienden a mostrar producciones más intensas y menos acústicas, con menor presencia de voz hablada. Además, los niveles de valence intermedios parecen funcionar mejor que emociones muy extremas. No se observa una relación clara entre la duración y el éxito, aunque las canciones excesivamente largas suelen asociarse a menor popularidad.

**¿Se puede predecir el éxito de una canción antes de su lanzamiento?**  
Sí, es posible realizar una predicción parcial del éxito de una canción utilizando características musicales disponibles antes de su lanzamiento. Estas variables permiten identificar tendencias generales y distintos niveles de potencial de éxito, aunque el modelo presenta limitaciones para predecir éxitos extremos o fenómenos virales.

**¿Se pueden identificar nuevos talentos o nichos musicales con potencial de éxito?**  
El análisis permite identificar canciones con características similares a las más exitosas incluso cuando pertenecen a artistas menos conocidos. Esto sugiere que el modelo puede utilizarse como una herramienta de apoyo para detectar nuevos talentos o nichos musicales con potencial de éxito.




## Conclusiones finales

A lo largo de este proyecto se ha desarrollado un modelo de Machine Learning para predecir el número de reproducciones de una canción en Spotify a partir de sus características musicales y de información disponible antes de su lanzamiento. Durante todo el proceso se ha seguido un flujo completo de un proyecto de aprendizaje automático, cuidando especialmente el orden de las fases y evitando en todo momento posibles filtraciones de información.

Los resultados obtenidos muestran que se trata de un problema complejo, ya que la variable objetivo presenta una gran variabilidad. Aun así, el análisis exploratorio y el modelado permiten identificar ciertos patrones entre las características musicales y el éxito de una canción. En este sentido, la transformación logarítmica de la variable objetivo resultó clave para mejorar el comportamiento del modelo, mientras que la eliminación de variables no aportó mejoras relevantes.

Entre los algoritmos probados, Random Forest fue el que mostró un mejor rendimiento y una mayor estabilidad, lo que justificó su elección como modelo final. El ajuste de hiperparámetros mediante distintos métodos condujo a conclusiones coherentes, lo que refuerza la confianza en la configuración seleccionada.

Aunque el modelo no permite predecir con total exactitud el éxito de una canción, sí puede servir como una herramienta de apoyo para entender qué características musicales tienden a asociarse con un mayor número de reproducciones. Además, el uso de visualizaciones gráficas a lo largo del proyecto ayudó a interpretar los datos y a responder de forma más clara a las preguntas de negocio planteadas, complementando los resultados obtenidos mediante el modelado.
