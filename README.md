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
Clona este repositorio:

Crea un entorno virtual e instala las dependencias:

bash
Copiar
Editar
python -m venv venv
source venv/bin/activate  # en Linux o Mac
venv\Scripts\activate     # en Windows

pip install -r requirements.txt
Configura tu base de datos en el archivo db_config.py con tus credenciales de PostgreSQL.

Ejecuta la aplicación:

bash
Copiar
Editar
python app.py
Abre tu navegador en: http://127.0.0.1:8050/

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

