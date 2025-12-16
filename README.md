# aprendizaje_automatico_proyecto
Autores

·Marta González Arroyo (marta.gonzalez@cunef.edu)

·Cristina Morcillo Ruiz (cristina.morcillo@cunef.edu)

·María Barbero Jiménez (maria.barbero@cunef.edu)

Link al repositorio:
https://github.com/mariabarberoc/aprendizaje_automatico_proyecto.git



# 1. Planteamiento del problema de negocio

En la industria músical actual Spotify y Youtube se han convertido en las principales platafromas indicadoras de éxito de una canción. Las discograficas o los propios artitas, publican canciones pero no siempre está claro qué características musicales conectan mejor con el público.

El objetivo principal de este proyecto busca desarrollar un modelo de Machine Learning capaz de predecir el nivel de éxito de una cancion a partir de sus características musicales y métricas de difusión.

Enfocado en predecir qué tipo de canciones funcionan mejor para ayudar a artistas que desean orientar su musica a lo que mejor conecta y alcanzar un mayor número de oyentes.

Además ayudar a discográficas a priorizar qué tipo de canciones promocionar e invertir en aquellas con mayor probabilidad de éxito,
Comprender el comportamiento del público según el tipo de canción, sus atributos sonoros o la interaccion en dos grandes plataformas. 
 
Para ello se analizan datos de grandes platafromas como Spotify y Youtube, considerando metricas de popularidad y variables que miden la sonoridad y composicion.



# 2. Planteamiento científico

Tipo de aprendizaje:
Se plantea un problema de aprendizaje supervisado, con un tarjet definido que permite medir de manera cuantitativa las el éxito en las canciones

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



Objetivo científico:
Entrenar un modelo capaz de relacionar las características musicales y la difusion digital con el éxito de las canciones, identificando patrones que permitan orientar decisiones estratégias en producción y promocion musical. Así como detectando talentos emergentes o nichos musicales con potencial.



# 3. Dataset

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



Preguntas a resolver:

•⁠  ⁠¿Qué tipo de canciones conviene priorizar e invertir por parte de una discográfica?

•⁠  ⁠¿Qué características musicales se asocian a las canciones más exitosas?


•⁠  ⁠¿Existen diferencias en los patrones de exito entre Spotify y Youtube en cuanto al éxito de las canciones?

•⁠  ⁠¿Se puede predecir el éxito de una canción antes de su lanzamiento?

•⁠  ⁠¿Se pueden identificar nuevos talentos o nichos musicales con potencial de éxito?



# 4. Diseño experimental

Para garantizar una evaluación realista y evitar filtraciones de información o data leakage, se separa el dataset en dos conjuntos independientes:

- train (spotify_limpio_train.csv): utilizado para el análisi exploratorio de datos (EDA), la limpieza, el feature engineering, el entrenamiento de modelos y selección de hiperparámetros. 

- Test (spotify_test.csv): reservado exclusivamente para la evaluación final del modelo.

La partición se realiza mediante una división aleatoria 80/20 (`test_size = 0.2`) con `random_state = 42`, de manera que los resultados sean reproducibles.

Utilizamos la validación cruzada sobre el conjunto de entrenamiento de esta forma podemos comparar modelos baseline y algoritmos candidatos, seleccionar variables/transformaciones, y ajustar hiperparámetros.

Sin olvidar que el conjunto de test permanece completamente aislado hasta la fase final.

Se utiliza un 20% de los datos como conjunto de test para contar con suficientes ejemplos no vistos que permitan evaluar el rendimiento final del modelo. Al mismo tiempo, esta proporción deja la mayor parte de los datos para entrenamiento, lo que resulta importante en un problema de regresión con una variable objetivo (Stream) muy variable.



# 5. Análisis exploratorio de datos (EDA) y limpieza

El análisis exploratorio de datos y la limpieza se realizan exclusivamente sobre el conjunto de entrenamiento `spotify_limpio_train.csv`, con el objetivo de evitar filtraciones de información y garantizar la validez del proceso de modelado.

En primer lugar, se eliminaron las variables `Views`, `Likes` y `Comments`, ya que representan métricas de interacción en YouTube que solo se generan después de la publicación de la canción. 
Dado que el objetivo del proyecto es predecir el éxito de una canción a partir de características musicales y variables disponibles de forma previa, estas columnas no resultan adecuadas como predictores.

Además, eliminamos las observaciones con valores nulos en la variable objetivo `Stream` previamente, ya que no es posible entrenar modelos de regresión cuando el target contiene valores faltantes.

Todas las operaciones de limpieza se aplicaron exclusivamente sobre el conjunto de entrenamiento.

Durante el EDA analizamos los tipos de variables y su correcta codificación, las distribuciones de las variables numéricas, la presencia de valores atípicos, y la relación entre los atributos y la variable objetivo `Stream`.

Este análisis permitió comprender el comportamiento de los datos, identificar posibles transformaciones y plantear hipótesis iniciales sobre qué características musicales podrían estar asociadas a un mayor número de reproducciones.



# 6. Baseline model

Como primer paso en la fase de modelado, se entrenó un modelo baseline con el objetivo de contar con una referencia inicial de rendimiento. Este modelo permite evaluar si las transformaciones posteriores y el uso de algoritmos más complejos aportan una mejora real.

El baseline se entrenó utilizando el conjunto de entrenamiento y se evaluó mediante validación cruzada. Como métrica de evaluación se utilizó el error cuadrático medio RMSE, ya que penaliza en mayor medida los errores grandes y es la adecuada para un problema de regresión como el planteado.

Los resultados obtenidos mostraron un RMSE elevado, lo que indica que el modelo base no presenta un buen rendimiento predictivo. Este resultado resulta útil como punto de comparación para evaluar la mejora conseguida en las siguientes etapas del proyecto, tanto con la aplicación de feature engineering como con el uso de modelos más avanzados.



# 7. Feature engineering

El proceso de feature engineering se realizó de forma progresiva y siempre sobre el conjunto de entrenamiento, utilizando validación cruzada para evaluar cada cambio y sin hacer uso del conjunto de test en ningún momento.

En primer lugar, se aplicamos una transformación logarítmica a la variable objetivo `Stream`. Esta decisión se tomó porque los valores de reproducciones son muy elevados y están muy dispersos, lo que provoca que los valores extremos tengan mucha influencia en el modelo. 
Al aplicar el logaritmo, se consigue una distribución más equilibrada y un comportamiento más estable del modelo, lo que se reflejó en una mejora del rendimiento al evaluarlo mediante validación cruzada.

Posteriormente, normalizamos algunas variables numéricas que presentan escalas muy diferentes entre sí, como `Tempo`, `Loudness` y `Duration_ms`. El objetivo de esta normalización fue evitar que variables con rangos muy grandes tuvieran un peso excesivo en el entrenamiento del modelo. 
Aunque esta transformación no supuso una mejora clara del rendimiento en todos los casos, permitió analizar mejor la contribución de cada variable.

A continuación, evaluamos la relevancia de las variables de forma individual y por pares, eliminándolas de manera iterativa y observando cómo variaba el RMSE medio obtenido mediante validación cruzada.

En este análisis pudimos observar que al eliminar variables como `Loudness`, `Speechiness` o `Acousticness`, el error aumentaba, lo que indica que estas variables aportan información relevante al modelo. En otros casos, como al eliminar `Tempo` o `Danceability`, no se observaron mejoras en el rendimiento.

En general, ninguna de las combinaciones probadas consiguió mejorar el RMSE respecto al modelo que incluía todas las variables. Por este motivo, se decidió mantener el conjunto completo de predictores para las siguientes fases del proyecto. Este resultado sugiere que la mejora del rendimiento debe venir principalmente del uso de modelos más complejos y no de una reducción adicional de variables.



# 8. Algoritmos cantidatos

Una vez definido el conjunto final de variables, probamos diferentes algoritmos vistos en clase de regresión con el objetivo de comparar su rendimiento y seleccionar el más adecuado para el problema planteado.

Además del modelo baseline, se entrenamos:

- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor

La comparación se realizó utilizando validación cruzada de 5 folds sobre el conjunto de entrenamiento y evaluando distintas métricas de error, entre ellas RMSE, MAE, MAPE y R² sorbre todos los modelos.

Con estos resultados, pudimos ver que el modelo de Random Forest presentaba el mejor rendimiento global, mostrando los valores más bajos de RMSE, MAE y MAPE, así como el valor más alto de R². Además, este modelo mostró una mayor estabilidad entre folds, con una menor variabilidad en los resultados.
Por este motivo, decidimos seleccionar Random Forest como algoritmo final para continuar con la fase de ajuste de hiperparámetros.



# 9. Selección de hiperparámetros

Después de comparar los distintos algoritmos, seleccionamos Random Forest como el modelo con mejor rendimiento. Ajustamos sus hiperparámetros para intentar mejorar aún más los resultados.

El ajuste se realizó únicamente para este modelo, utilizando validación cruzada de 5 folds y tomando el RMSE como métrica de referencia. Para ello usamos RandomizedSearchCV, ya que permite probar distintas combinaciones de hiperparámetros de forma más eficiente que GridSearchCV y reduce el coste computacional.

Durante todo este proceso, al igual que anteriormente no utilizamos el conjunto de test, lo mantenemos separado para poder evaluar el modelo final de forma justa.



# 10. Modelo final y evaluación 

Una vez seleccionados el algoritmo y los hiperparámetros, entrenamos el modelo final utilizando todo el conjunto de entrenamiento `spotify_limpio_train.csv`, con el objetivo de aprovechar la mayor cantidad posible de datos.

El modelo final corresponde a un Random Forest con los hiperparámetros obtenidos en la fase anterior. Tras el entrenamiento, el rendimiento del modelo se evaluó únicamente sobre el conjunto de test 'spotify_test.csv`, que no había sido utilizado en ninguna de las etapas previas.

Para la evaluación empleamos distintas métricas de regresión, entre ellas RMSE, MAE, MAPE y R². Estas métricas permiten analizar el error del modelo desde distintos puntos de vista y obtener una visión más completa de su rendimiento.

Los resultados obtenidos en el conjunto de test proporcionan una estimación realista de la capacidad del modelo para predecir el número de reproducciones de canciones no vistas.
















