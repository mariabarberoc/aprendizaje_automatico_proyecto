# aprendizaje_automatico_proyecto
# aprendizaje_automatico_proyecto
Autores

·Marta González Arroyo (marta.gonzalez@cunef.edu)

·Cistina Morcillo Ruiz (cristina.morcillo@cunef.edu)

·María Barbero Jiménez (maria.barbero@cunef.edu)

Link al repositorio:
https://github.com/mariabarberoc/aprendizaje_automatico_proyecto.git


Origen dataset:

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
    
·Key: tonalidad musical de la cancion, se presenta codificada como número entero 

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


Objetivos proyecto y descripción del problema de negocio

En la industria músical actual Spotify y Youtube se han convertido en las principales platafromas indicadoras de éxito de una canción. Las discograficas o los propios artitas, publican canciones pero no siempre está claro qué características musicales conectan mejor con el público.

El objetivo principal de este proyecto busca desarrollar un modelo de Machine Learning capaz de predecir el nivel de éxito de una cancion a partir de sus características musicales y métricas de difusión.

Enfocado en predecir qué tipo de canciones funcionan mejor para ayudar a artistas que desean orientar su musica a lo que mejor conecta y alcanzar un mayor número de oyentes.

Además ayudar a discográficas a priorizar qué tipo de canciones promocionar e invertir en aquellas con mayor probabilidad de éxito,
Comprender el comportamiento del público según el tipo de canción, sus atributos sonoros o la interaccion en dos grandes plataformas. 
 
Para ello se analizan datos de grandes platafromas como Spotify y Youtube, considerando metricas de popularidad y variables que miden la sonoridad y composicion.


Pranteamiento del problema:

Tipo de aprendizaje:
Se plantea un problema de aprendizaje supervisado, con u tarjet definido que permite medir de manera cuantitativa las el éxito en las canciones

Variable objetivo / Target:
En este caso, principalmente será Stream, el número de reproducciones de cada canción en Spotify, aunque se puede considerar Views, representa las visualizaciones del videoclip en Youtube o una combinación de métricas.

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

Likes

Comments

Official_video 

Licensed


Objetivo científico:
Entrenar un modelo capaz de relacionar las características musicales y la difusion digital con el éxito de las canciones, identificando patrones que permitan orientar decisiones estratégias en producción y promocion musical. Así como detectando talentos emergentes o nichos musicales con potencial.


Preguntas a resolver:

•⁠  ⁠¿Qué tipo de canciones conviene priorizar e invertir por parte de una discográfica?

•⁠  ⁠¿Qué características musicales se asocian a las canciones más exitosas?

•⁠  ⁠¿Infuyen factores de difusion como videoclips oficiales en Youtube o el número de likes en la popularidad de una canción?

•⁠  ⁠¿Existen diferencias en los patrones de exito entre Spotify y Youtube en cuanto al éxito de las canciones?

•⁠  ⁠¿Se puede predecir el éxito de una canción antes de su lanzamiento?

•⁠  ⁠¿Se pueden identificar nuevos talentos o nichos musicales con potencial de éxito?