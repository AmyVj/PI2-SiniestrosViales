# Proyecto de Análisis de Datos sobre Accidentes Viales en CABA del periodo 2016 - 2021

## Introducción 

En el presente proyecto se ilustra el papel de un Data Analyst, quien integra el equipo de analistas de datos de una compañía consultora. El Observatorio de Movilidad y Seguridad Vial (OMSV) es un centro de estudios que se encuentra bajo la responsabilidad de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA), quien solicita la elaboración de un proyecto de análisis de datos.

El propósito de este proyecto consiste en generar información que permita a las autoridades locales adoptar medidas para reducir la cantidad de víctimas fatales de los accidentes viales ocurridos en la ciudad de CABA. Con el fin de lograr tal fin, se ha presentado un registro de homicidios en accidentes viales ocurridos en la Ciudad de Buenos Aires durante el período 2016-2021.

Se espera que los productos finales sean un informe detallado de las tareas llevadas a cabo, las metodologías adoptadas y las principales conclusiones, así como una presentación de un dashboard interactivo que facilite la interpretación de la información y si se realiza un análisis.

## Contexto 🚗

Los accidentes viales, también conocidos como accidentes de tráfico o accidentes de tránsito, son eventos que involucran vehículos en las vías públicas y que pueden presentar diversas causas, tales como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, choques con objetos fijos o caídas de vehículos. Los sucesos ocurridos pueden tener consecuencias que van desde perjuicios materiales hasta lesiones graves o fatales para los implicados.

La Ciudad Autónoma de Buenos Aires, situada en la provincia de Buenos Aires, Argentina, no es una excepción, sino que los accidentes viales son una preocupación crucial debido al elevado volumen de tráfico y la densidad poblacional. Los sucesos ocurridos pueden tener un impacto significativo en la seguridad de los residentes y visitantes de la ciudad, así como en la infraestructura vial y los servicios de emergencia.

El censo poblacional realizado en el año 2022 indica que la población de CABA tiene aproximadamente 3,120.612 habitantes en una superficie de 200 $km^2$, lo que equivale a una densidad aproximada de 15,603 $hab/km^2$ ([Fuente](https://www.argentina.gob.ar/caba#:~:text=Poblaci%C3%B3n%3A%203.120.612%20habitantes (Censo) En el mes de Julio del año 2023, se registró un total de 12,437,735 vehículos transitando por los peajes de las autopistas de acceso a CABA, a través de la página web https://www.estadisticaciudad.gob.ar/eyc/?p=41995) Por consiguiente, la prevención de accidentes viales y la implementación de medidas efectivas son fundamentales para abordar este asunto de manera adecuada.

## Datos 📊

Para el presente proyecto, se llevó a cabo la aplicación denominada "Bases de Víctimas Fatales en Siniestros Viales", que se encuentra en formato Excel y contiene dos pestañas de datos.

Se trata de una fila de hecho con un id único, así como las variables temporales, espaciales y participantes asociadas al mismo.
VICTIMAS: contiene una lista de cada víctima de los hechos y las variables de edad, sexo y modo de desplazamiento asociadas a cada víctima. Se establece una conexión entre los hechos a través del índice del hecho.

En el presente documento, denominado "datos\NOTAS_HOMICIDIOS_SINIESTRO_VIAL.pdf", se detallan todas las definiciones implementadas en los datos y en el desarrollo de este proyecto. Por otro lado, en este link se encuentran los datos utilizados en el análisis.

## Tecnologías usadas 💻

Para la elaboración de este proyecto, se empleó la herramienta Python y Pandas para la extracción, transformación y carga de los datos, así como para el análisis exploratorio de los datos. A continuación se presentan los resultados del análisis.

A continuación, se realizó webscraping para obtener datos complementarios para el cálculo de la población en 2021 utilizando la librería BeautifulSoup. Los detalles se explican aquí](Notebooks\02_Datos_poblacion_CABA.ipynb)

En última instancia, para la elaboración de un dashboard interactivo, se emplea Power BI, el cual puede ser consultado en el siguiente sitio web (PI2_homicidios pbix)

## ETL y EDA. 📊

En primer lugar, se llevó a cabo un procedimiento de extracción, transformación y carga de los datos (ETL), tanto de "HECHOS" como de "VÍCTIMAS", en el cual se examinaron nulos y duplicados de los registros, se eliminaron columnas reducidas o con numerosos valores faltantes, entre otras tareas. Una vez completado este proceso para los dos conjuntos de datos de "Homicidios", se procedió a unir los dos en uno solo denominado "HOMICIDIOS".

En segundo lugar, se llevó a cabo un análisis exploratorio exahustivo (EDA), con el propósito de identificar patrones que permitan generar información que permita a las autoridades locales adoptar medidas para disminuir la cantidad de víctimas fatales de los accidentes viales. Todos los detalles de este análisis se encuentran en la siguiente página: Notebooks\01_Procesamiento_Datasets-ETL-EDA.ipynb.

## Estudio de los Datos 📈

La variable inicial que se examinó fue la variable temporal, con el fin de comprender la distribución de los homicidios en diversas escalas temporales. La distribución anual de la cantidad de víctimas fatales se encuentra en un 60% en los primeros tres años del conjunto de datos, con una disminución significativa en el año 2020, debido a la cuarentena por COVID 19. El comportamiento a lo largo del año, es decir, la variación mensual. A pesar de que para todo el conjunto de datos se encuentra marcada, con un incremento en la cantidad de víctimas en Diciembre, esta tendencia no se puede apreciar de manera clara entre los diferentes años. Este resultado de la mayor cantidad de víctimas en Diciembre está influido por la flexibilización de las medidas adoptadas por la cuarentena.

Posteriormente, al descender en la escala temporal, se puede constatar que el 70% de los afectados sufrieron la muerte durante el transcurso de lunes y viernes, lo que podría sugerir que se debe al traslado diario al trabajo. Sin embargo, en la distribución semanal no se evidencian diferencias significativas entre los diferentes días. En otras palabras, la cantidad de víctimas que se encuentran en peligro en un día sábado o domingo, se estima aproximadamente el mismo.

Si se examinan las franjas horarias, las mayores víctimas, que representa el 12% de las víctimas, se presentaron entre las 6 y 8 de la mañana, lo que también hace pensar en el horario de ingreso a los trabajos. Sin embargo, si se examina la franja en cuestión, se puede constatar que el 55% de las víctimas resultaron de sucesos acontecidos durante el fin de semana.

La última acción se llevó a cabo fue examinar el perfil de la víctima. En primer lugar, se observa que el 73% de las víctimas son masculinas. El porcentaje del individuo que padece la muerte se encuentra en un rango etario comprendido entre los 25 y 25 años de edad, siendo el 84% de ellos femeninos.

Si se aprecia el papel de la víctima, es decir, la posición relativa que ocupaba al momento del suceso, el 48% era conductor. En particular, este 48% se distribuye en un 77% de víctimas que se movían en motocicleta y el 19% en automóvil. Según el medio de transporte en cuestión, el 42% de las víctimas son conductores de moto, de los cuales el 88% de los conductores de moto son masculinos.

Si se examina la responsabilidad en el suceso, es decir, el vehículo que ocupaba el acusado, se constata que en el 29% de los casos se trataba del automóvil, mientras que en el 75% se encuentran responsabilidades de vehículos como auto, colectivos y camiones.

Finalmente, se buscaron patrones en la distribución espacial de los sucesos. Lo que resulta relevante de este análisis es que en todas las comunas de CABA se observan como factor común los accidentes en las avenidas, que son vías arteriales de calzada ancha, de al menos 13 metros. El 62% de las víctimas fallecieron en avenidas. En particular, el 82% de los sucesos ocurrieron en el emplazamiento de las avenidas con otra vía. Esta es una actitud que se mantiene entre los diferentes años. En relación al papel de la víctima en el momento de la ocurrencia, se distingue entre vehículos de motocicleta y vehículos de peatón.

## KPI 🎯

Se establecieron tres objetivos para reducir la cantidad de víctimas muertes en los accidentes viales. Se proponen tres indicadores de rendimiento clave o KPI.

1. **Reducción de la tasa de homicidios en siniestros viales:**
    - En CABA, reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.
    - Se calculó la población total en 2021 a partir de los censos poblacionales del año 2010 y 2022.
    - En este caso, en 2021, la tasa de homicidios en siniestros viales fue de 1.77, lo que significa que, durante los primeros seis meses del año 2021, hubo aproximadamente 1.77 homicidios en accidentes de tránsito por cada 100,000 habitantes. Ahora, el objetivo es reducir esta tasa en un 10% para el próximo semestre de 2021, que es de $1.60. Cuando se calcula el KPI para este período, se descubre que la tasa de homicidios en siniestros viales fue de 1.35, lo que significa que en 2021 se cumplirá con el objetivo propuesto.

  Su fórmula es:

$\text{Tasa de homicidios en siniestros viales} = \frac{\text{Número de homicidios en siniestros viales}}{\text{Población total}}·100,000$



2. **Reducción de accidentes mortales de motociclistas:**
    - En el último año, en CABA, hubo menos accidentes mortales de motociclistas que en el año anterior.
    - Se considera el año actual del 2021 y el año actual del 2020.
    - Se calculó la cantidad de accidentes mortales de motociclistas en 2020, que fue de 44.00. El objetivo es alcanzar el objetivo de cumplir con el objetivo de reducir el 7% de los accidentes en 2020. La cantidad de accidentes mortales de motociclistas en 2021 fue de 64.29, lo que supone que aumentaron un 64% las muertes de conductores de motociclistas respecto del 2021.

3. **Reducción de la tasa de homicidios en las avenidas:**
    - En el último año, en CABA, hubo menos homicidios en las calles que en el año anterior.
    - La tasa de muertes en las avenidas es el número de muertes fatales en accidentes de tránsito en avenidas por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso anual.

La fórmula para medir la evolución de los accidentes mortales con víctimas en moto es:
    $\text{Cantidad de accidentes mortales de motociclistas} = -\frac{\text{Víctimas moto año anterior - Víctimas moto año actual}}{\text{Víctimas moto año anterior}}·100$

 Donde:
    - $\text{Víctimas moto año anterior}$: Número de accidentes mortales con víctimas en moto en el año anterior
    - $\text{Víctimas moto año actual}$: Número de accidentes mortales con víctimas en moto en el año actual 
      
- En este caso, se calculó la cantidad de personas muertas en las calles en 2020, que fue de 1.68. Se encontró el objetivo del año siguiente, que fue reducir el 10% de los homicidios respecto al año anterior. Al calcular la tasa de homicidios en las avenidas para el año 2021, la misma resultó de 1.97, lo que significa que se superó el objetivo, aumentando la tasa de mocidios en avenidas respecto al año anterior.

  En la siguiente imagen se aprecian los rendimientos de los tres KPI propuestos.

![KPI](![image](https://github.com/AmyVj/PI2-SiniestrosViales/assets/140218086/fd3e8263-0fc1-4ea6-ad9b-fafe094182a5)
)

## Conclusión y recomendación

- En los años 2016 a 2021 se registraron 717 muertos en accidentes de tránsito. La mayoría de los muertos se registró en la semana. El 12% de los hechos ocurren entre las 6 y las 8 de la mañana, pero durante los fines de semana. Diciembre es el mes que resulta con el máximo de fallecimientos en el período analizado.
- La mayoría de las víctimas mortales fueron de origen masculino con un 77%, de los cuales casi el 50% tenían entre 25 y 44 años de edad. En cuanto al tipo de usuario, el 42% de los usuarios fueron conductores de vehículos. La mayoría de los asesinatos se produjo en algún lugar de las avenidas de CABA, siendo el 82% de ellos en un trayecto de la autopista con otra calle. En consecuencia, el 75% de los sucesos ocurrieron en áreas de aparcamiento.
- En última instancia, para el segundo semestre de 2021, se alcanzó el objetivo de disminuir la tasa de accidentes mortales en accidentes viales, pero no se alcanzaron los objetivos de disminuir la cantidad de accidentes mortales en motociclistas ni en avenidas para el año 2021 en comparación con el año 2020.
- En consecuencia, se establecen las siguientes recomendaciones:
  - Mantener un seguimiento constante de los objetivos planteados acompañado de campañas puntuales, especialmente a los conductores de motocicletas y usuarios de las avenidas.
  - Se debe reforzar las campañas de seguridad vial entre los días viernes y lunes, incrementando de manera especial en el mes de Diciembre.
  - Establecer campañas de conducir seguras en avenidas y cruzes de calles.
  - Se deberán dirigir las acciones de seguridad hacia el sexo masculino, especialmente en lo que respecta a la conducción en moto, con una edad comprendida entre los 15 y 44 años.
