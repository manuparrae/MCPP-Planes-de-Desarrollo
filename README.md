# MCPP-Planes-de-Desarrollo

## Análisis algunos de los primeros discursos de desarrollo de Colombia (1961-1982)


![Diseño sin título](https://user-images.githubusercontent.com/92605756/142953200-5d09aa52-1716-41f2-9d40-9762de2b9703.jpg)


## ¿De qué trata mi proyecto y cuáles fueron mis motivaciones?
En este trabajo me intereso por analizar los cinco primeros planes de desarrollo que se hicieron en Colombia, a nivel discursivo: Desarrollo económico y social (1961-1970) - Alberto Lleras Camargo; Planes y programas de desarrollo (1969-1972) - Carlos Lleras Restrepo; Las cuatro estrategias (1970-1974) - Misael Pastrana; Para cerrar la brecha (1974-1978) - Alfonso López, y Cambio con equidad (1982-1986) - Belisario Betancur. Este tema se desprende de mi tesis de pregrado en historia, en la que estudio el diseño y funcionamiento de los créditos agrarios para el desarrollo agrícola en Colombia, entre 1950 y 1980. Este análisis del discurso se enmarcaría el primer capítulo de mi tesis, en el que estudio cuáles eran las concepciones de desrrollo que cada gobierno tenía, cuáles eran sus prioridades frente al desarrollo y qué se proponía hacer para que Colombia se convirtiera en un país desarrollado. 

A mediados del siglo XX, economistas, políticos y burócratas del Estado convergieron en que la planeación estatal era necesaria para formular mejores políticas públicas y aumentar la efectividad de los programas económicos, sociales y políticos. Como lo afirma Olga Lucía Zapata Cortés, "los planes de desarrollo en Colombia se reconocen como el instrumento por medio del cual se gobierna y planifica el desarrollo social, económico y cultural del país" (2020, p.245). De manera que un análisis histórico de las políticas para el desarrollo en el país debe necesariamente pasar por el estudio de estos planes. Así mismo, entender la historicidad de los planes de desarrollo, de su estructura y propósitos, nos permite reflexionar sobre aquellos diseñados en épocas recientes. En otras palabras, es un tema que está lejos de hallarse relegado al pasado.

Dicho esto, los temas y preguntas específicas que este proyecto busca tratar y resolver son:
* ¿Cuáles eran las preocupaciones centrales de cada plan de desarrollo?
* ¿Cuáles son las continuidades observables a nivel discursivo en los planes?
* ¿Cuáles son las rupturas observables a nivel discursivo en los planes?
* ¿Cómo se pueden interpretar los resultados?¿Tienen sentido los resultados con lo que efectivamente ocurrió en la práctica?

## Metodología

### Accediendo a la materia prima del análisis
Es sencillo encontrar los planes de desarrollo de Colombia en la página oficial del Departamento Nacional de Planeación, por lo que, en principio pensé en hacer web scrapping a los pdf que se encontraban como vínculo directo de cada uno de los planes. Ver: https://www.dnp.gov.co/Plan-Nacional-de-Desarrollo/Paginas/Planes-de-Desarrollo-anteriores.aspx
No obstante, lo que en apariencia era sencillo, terminó siendo el mayor reto para desarrollar este proyecto. Los pdf que se encuentran en dicha página no pueden ser leídos, es decir, cuando uno importa los archivos a Python, aparecen signos y letras que están muy lejos de ser el contenido real de los planes. 
Dicho esto, la primera herramienta que utilicé fue la librería "ocrmypdf", que requiere la instalación de varias extensiones, pero que definitivamente cumple su objetivo de convertir cualquier pdf con este tipo de problemas a uno que puede ser leído. 

### Limpieza y procesamiento de los datos
* NLTK
* Matplotlib
* Pandas
* Stylecloud

El procesamiento de los datos lo hice principalmente con NLTK, que me permitió analizar los archivos convertidos a ".txt". Con ello, me detuve a observar la longitud de cada plan (en número de palabras), limpié los datos para eliminar números, mayúsculas y "stopwords", para posteriormente ver la frecuencia de las palabras y las "most common words". Así mismo, decanté el análisis a palabras de interés específicas, para ver su frecuencia en cada plan de desarrollo. Y, con algunas de ellas, observé qué otras palabras aparecían al lado para dar contexto a su empleo. 
Algunas de mis palabras de interés eran:
* *Desarrollo: centro de los planes y con la cual pude ver si se hablaba de desarrollo en general, de desarrollo social, de desarrollo económico, de desarrollo agrícola, etc. 
* *Crédito: Corresponde a un interés que se desprende de mi tesis (quería ver qué tan presente estaba este tema en cada plan).
* *Productividad: Analizar el contexto histórico muestra que el impulso a la productividad agrícola e industrial fue constante en estas décadas de desarrollo.
* *Rural-Urbano: Quería ver si primaba uno de los sectores frente al otro, en cada uno de los planes

A partir de lo anterior, cree DataFrames con Pandas, para mostrar las frecuencias de las palabras de interés. Y, después, quise visualizar dos outputs:
*Un histograma por cada plan de desarrollo que me mostrara la frecuencia de mis palabras de interés
*Una nube de palabras por cada plan de desarrollo, que me mostara la frecuencia de todas las palabras, exceptuando stopwords y otras que no eran de interés 

## Resultados
Cada uno de los planes de desarrollo seleccionados varía con respecto a sus temas centrales. Por ejemplo, el plan de Alberto Lleras Camargo muestra que temas como la educación y lo social prima sobre la industria y el sector de la construcción, mientras que el de Belisario Betancur Cuartas el sector de la construcción prima sobre el sector rural y agropecuario. Esto halla su explicación en el contexto histórico, que nos muestra que, a diferencia de los gobiernos de Lleras Camargo y Lleras Restrepo que impulsaron una reforma agraria y dieron un lugar importante al sector rural y a los aspectos más sociales del desarrollo, los goniernos de Misael Pastrana y López Pumarejo defendieron la migración del campo a la ciudad y el impulso del sector de construcción urbana (Ver: Jesús Antonio Bejarano, Carlos Caballero Argáez y Darío Fajardo). 

![Camargo-PI](https://user-images.githubusercontent.com/92605756/142957239-ea08d70d-2eb0-4d47-b15a-47e8345dfd51.jpeg)
![Pastrana-PI](https://user-images.githubusercontent.com/92605756/142957281-a2f0e203-0bbe-46f7-9ac6-6cd28693136c.jpeg)

Sin embargo, llama la atención que, aunque en la práctica las políticas públicas de la década de 1970 tuvieron un tinte menos social y rural que las de la década de 1960 (ver, por ejemplo, Pacto de Chicoral, que enterró toda propuesta de reforma agraria), en los planes de Pastrana, López y Betancur palabras como "educación,"social" y "salud" sigan teniendo una frecuencia considerable (incluso más que los primero planes). Esto lleva a pensar en la potencialidad de metodología como esta para encontrar fisuras entre los que se propone a nivel discursivo y lo que se ejecuta realmente en la práctica. 

### Nubes de palabras
* Alberto Lleras Camargo
![Lleras-WC](https://user-images.githubusercontent.com/92605756/142957559-42d554b7-3954-49aa-a5be-643a49265978.jpeg)
* Carlos Lleras Restrepo
![Restrepo-WC](https://user-images.githubusercontent.com/92605756/142957594-0ebff773-a0f6-4276-bd3c-3b8bec31591a.jpeg)
* Misael Pastrana Borrero
![Pastrana_WC](https://user-images.githubusercontent.com/92605756/142957607-b0192825-e661-4aad-b9dd-2980fb9d643a.jpeg)
* Alfonso López Michelsen
![López_WC](https://user-images.githubusercontent.com/92605756/142957624-b47d7d61-8578-45f1-a796-f3172cc92319.jpeg)
* Belisario Betancur Cuartas
![Betancur-WC](https://user-images.githubusercontent.com/92605756/142957645-a867c86c-0242-4ad4-8a7a-e9e89af0c8c8.jpeg)

## Reflexiones Finales
* Hay que resaltar la utilidad de la librería *ocrmypdf* para analizar textos que, por haber sido producidos en años anteriores, no se encuentran de primera mano como pdf leíbles. 
* Es importante resaltar la necesidad de ubicar los planes de desarrollo y fuentes similares en sus contextos históricos, pues estos pueden complejizar su contenido. 
* Es fundamental cruzar los planes de desarrollo y fuente similares con otros tipos de fuente, pues este análisis nos pueden mostrar fisuras entre discurso y práctica.

## Bibliografía 

* Bejarano, Jesús Antonio (1991) “Industrialización y política económica 1950-1976”, En: *Colombia hoy; Perspectivas hacia el siglo XXI*, Jorge Orlando Melo (ed). Bogotá: Siglo XXI Editores. 
* Caballero Argáez, Carlos (2016) *La economía colombiana del siglo XX: Un recorrido por la historia y sus protagonistas*, Bogotá: Debate. 
* Departamento Nacional de Planeación (s.f.) "Planes de desarrollo anteriores". Recuperado de: https://www.dnp.gov.co/Plan-Nacional-de-Desarrollo/Paginas/Planes-de-Desarrollo-anteriores.aspx
* Fajardo, Darío (2002) “Tierra, poder político y reformas agraria y rural”, *Cuadernos Tierra y Justicia*, n°1. 
* Zapata Cortés, Olga Lucía. (2020). “Reflexión sobre los planes de desarrollo en Colombia”. *Bitácora Urbano Territorial*, 30 (III): 233-246. https://doi.org/10.15446/bitacora.v30n3.86811
