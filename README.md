# Prueba
# Sistema Analítico para la Visualización de Portafolios de Inversión
Este proyecto fue desarrollado como parte de una prueba técnica para la Gerencia Analítica de Inversiones 2025 en Valores Bancolombia. El objetivo fue construir un sistema interactivo que permita analizar portafolios de inversión de diferentes clientes, clasificándolos por banca, perfil de riesgo, macroactivos y su evolución mensual.

## Tecnologías Utilizadas
Python 3.11

Dash / Plotly para visualizaciones interactivas.

PostgreSQL 17 para la gestión de bases de datos relacionales.

Pandas para el análisis de datos.

SQLAlchemy para la conexión entre Python y la base de datos.

##Estructura del Proyecto
bash
Copiar
Editar
proyecto_inversiones/
│
├── app.py                  # Aplicación principal en Dash
├── db_config.py            # Configuración de conexión a PostgreSQL
├── requirements.txt        # Librerías necesarias
├── README.md               # Este archivo



## Instrucciones para Ejecutar el Proyecto
Para ejecutar este proyecto, primero se debe clonar el repositorio con el comando git clone https://github.com/TU_USUARIO/TU_REPOSITORIO.git y luego entrar a la carpeta del proyecto con cd TU_REPOSITORIO. Una vez dentro, se recomienda crear un entorno virtual para aislar las dependencias utilizando python -m venv venv. Este entorno se activa con venv\Scripts\activate en Windows o source venv/bin/activate en Mac/Linux. Luego, se deben instalar las dependencias necesarias con pip install -r requirements.txt. Si no se cuenta con el archivo requirements.txt, se puede generar con pip freeze > requirements.txt después de instalar las bibliotecas usadas como pandas, dash, sqlalchemy y psycopg2.

El siguiente paso es configurar la base de datos. Para esto se debe tener instalado PostgreSQL y crear una nueva base de datos llamada, por ejemplo, aba_analytics. Esto puede hacerse desde pgAdmin o con el comando CREATE DATABASE aba_analytics; en consola. Luego, dentro del código Python, se debe establecer una conexión a esa base de datos utilizando SQLAlchemy, con una línea como engine = create_engine("postgresql://usuario:contraseña@localhost:5432/aba_analytics"), reemplazando usuario y contraseña por las credenciales locales.

Con la base de datos lista, se deben cargar los datos. Como los archivos .csv no están incluidos en este repositorio por políticas de confidencialidad, se deben ubicar manualmente en la carpeta adecuada y ejecutar el script load_data.py, el cual se encarga de leer los archivos y volcarlos en PostgreSQL. Este script puede construirse usando pandas.read_csv() para leer los datos y .to_sql() para cargarlos en las tablas respectivas.

Una vez cargados los datos, se ejecuta el sistema analítico con python app.py, lo cual inicia un servidor local de Dash. Para visualizar el dashboard se debe abrir el navegador y dirigirse a http://127.0.0.1:8050/, donde se podrá interactuar con los filtros por mes, perfil de riesgo y tipo de banca, así como visualizar la evolución de los macroactivos a lo largo del tiempo. El sistema permite observar la distribución de inversiones por cliente, banca, perfil de riesgo y tipo de macroactivo (FICS, renta fija, renta variable, etc.).

Este proyecto fue desarrollado usando Python 3.9, PostgreSQL 17, Dash y herramientas estándar de análisis de datos. Se recomienda el uso de entornos virtuales y evitar subir credenciales o datos sensibles al repositorio.

## Funcionalidades del Dashboard
Filtro por banca, perfil de riesgo y mes.

Visualización de los montos por macroactivos como Renta Fija, Renta Variable y FICs.

Comparación mensual de la evolución de los portafolios.

Gráficas dinámicas que permiten detectar tendencias y patrones de comportamiento.

## Conclusiones Técnicas
Se logró implementar un pipeline de extracción, transformación y visualización de datos desde PostgreSQL a Dash.

Se usaron buenas prácticas en la conexión y manipulación de datos, asegurando modularidad del código (db_config, app.py).

## Conclusiones de Negocio
En el perfil sin definir, se evidenció una fuerte presencia en Renta Variable (~1.057B) y FICs (~1.7B), comportamiento constante en todos los meses.

El perfil conservador, que incluye empresas, banca privada y pymes, opta mayoritariamente por FICs como vehículo de inversión, lo cual sugiere una preferencia por diversificación controlada.

El perfil moderado muestra una mayor variedad: inversiones más repartidas entre renta fija, variable y FICs.

En el perfil riesgoso, destaca una alta incidencia en renta variable, con menor peso en FICs, lo cual refleja un apetito elevado por riesgo y potencial rendimiento.

Estos hallazgos permiten a la organización perfilar mejor a sus clientes y ajustar sus estrategias de asesoría y portafolio.

## Conclsuiones 
Estructura constante de macroactivos en perfil sin definir:
Para el mes 1 y los meses posteriores, se observa una estructura estable de inversión en el perfil sin definir, con una alta asignación a FICS (~1.7B) y Renta Variable (~1.057B). Esto sugiere un comportamiento predeterminado por parte de los clientes sin perfil asignado.

Predominio de FICS en perfil conservador:
En el perfil conservador, las bancas como Empresas, Banca Privada y Pymes muestran una clara preferencia por FICS como vehículo principal de inversión, alineado con su aversión al riesgo y necesidad de liquidez o estabilidad.

Diversificación en perfil moderado:
El perfil moderado presenta una asignación balanceada con mayor peso en Renta Fija, presencia media de FICS, y una menor, pero existente, participación en Renta Variable. Esto muestra un comportamiento más estratégico buscando retornos sin comprometer del todo la seguridad.

Alta exposición a Renta Variable en perfil riesgoso:
En este perfil se evidencia una fuerte preferencia por Renta Variable, lo cual es coherente con su tolerancia al riesgo y la búsqueda de mayor rentabilidad. Los FICS también están presentes como vehículo complementario.

para aquellos clientes sin perfil definido se evidencia una significativa inversión en FICS y Renta Variable, lo cual abre la posibilidad de implementar campañas de perfilamiento activo que faciliten un manejo más adecuado del riesgo y contribuyan al cumplimiento normativo. Además, el uso masivo de FICS en clientes conservadores y sin perfil sugiere que estos fondos son percibidos como seguros, flexibles y de fácil acceso, por lo que se puede profundizar en estrategias de mercadeo enfocadas en esta herramienta. En el caso del perfil moderado, la combinación diversa de inversiones indica una mayor adaptabilidad, ofreciendo la oportunidad de diseñar productos híbridos o escalonados que se adapten a sus necesidades y a su predisposición a la diversificación. Por último, en el perfil riesgoso se observa una fuerte preferencia por rentabilidad, lo que plantea la conveniencia de crear soluciones que integren renta variable con coberturas o derivados, de modo que se ofrezca protección sin sacrificar el potencial de altos retornos.

