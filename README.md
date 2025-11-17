# RAG-LLM-Project
En este proyecto combinamos modelos de lenguaje con recuperación semántica para convertir preguntas en lenguaje natural en consultas SQL. Usamos un enfoque RAG simplificado, donde ejemplos de preguntas y consultas SQL se embeben y recuperan según su similitud con la consulta del usuario.

<img width="1024" height="1024" alt="flujo" src="https://github.com/user-attachments/assets/b0bfbb2f-4147-4498-83e4-a17cbeedcfac" />


Estructura del proyecto

* setup_netflix_sqlite.py: Script para crear y poblar la base de datos SQLite.

* examples.json: Ejemplos de preguntas y consultas SQL para guía.

* precalcular_embeddings.py: Calcula y guarda embeddings para los ejemplos.

* generar_consulta.py: Lógica para buscar ejemplos similares y generar consultas con Gemini.

* schema_manager.py: Maneja el esquema de la base de datos para validar consultas y construir prompts.

* main.py: Interfaz web con Streamlit para interactuar con el sistema.

* netflix.db: Base de datos SQLite con los datos de ejemplo.

Instrucciones para iniciar y ejecutar la aplicación

1. Asegúrate de tener Python instalado
Preferiblemente Python 3.8 o superior.

2. Instala las dependencias
pip install -r requirements.txt

4. Ejecuta el script para crear y poblar la base de datos
python setup_netflix_sqlite.py
Esto generará el archivo netflix.db con los datos de ejemplo necesarios.

5. Genera los embeddings de los ejemplos
python precalcular_embeddings.py
Este paso crea el archivo ejemplos_embeds.pkl que ayuda a la búsqueda semántica para la generación de consultas.

6. Configura la clave de API para Gemini
Crea un archivo .env en la raíz del proyecto con la siguiente variable (reemplaza con tu propia API key):
GEMINI_API_KEY=tu_api_key_aqui

6. Ejecuta la aplicación Streamlit
streamlit run main.py
Esto abrirá la interfaz web donde podrás escribir preguntas en lenguaje natural y ver las consultas SQL generadas junto con su análisis.
