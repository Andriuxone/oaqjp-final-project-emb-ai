# Guía de evidencias – Proyecto Final: Detector de Emociones

Repositorio local: `C:\proyectos\oaqjp-final-project-emb-ai`
Repositorio GitHub (cuando lo publiques): `https://github.com/Andriuxone/oaqjp-final-project-emb-ai`

Las salidas de terminal y las capturas **tienen que salir del laboratorio de IBM Skills Network**. La API de Watson solo responde dentro de ese entorno, y el evaluador espera ver la ruta `/home/project/final_project` en las salidas.

---

## Paso 0 – Publicar el repositorio en GitHub (una sola vez)

1. Entra en https://github.com/ibm-developer-skills-network/oaqjp-final-project-emb-ai con la cuenta **Andriuxone** y pulsa **Fork**. Deja el nombre `oaqjp-final-project-emb-ai` y confirma que el repo es **Public**.
2. En tu PC (PowerShell o Git Bash):

```bash
cd C:\proyectos\oaqjp-final-project-emb-ai
git push -u origin HEAD
```

(El remoto `origin` ya apunta a tu fork y el commit con todo el código ya está hecho.)

## Paso 1 – Preparar el laboratorio de IBM

En la terminal del laboratorio:

```bash
cd /home/project
git clone https://github.com/Andriuxone/oaqjp-final-project-emb-ai.git final_project
cd final_project
python3 -m pip install requests flask pylint
```

---

## Pregunta 1 – Tarea 1 (URL)
Envía esta URL:
`https://github.com/Andriuxone/oaqjp-final-project-emb-ai/blob/main/README.md`
(El README ya dice `# Final Project`.)

## Pregunta 2 – Tarea 2, Actividad 1 (código)
Copia y pega el contenido de `evidencias/2a_emotion_detection`.

## Pregunta 3 – Tarea 2, Actividad 2 (salida de terminal)
En el laboratorio, dentro de `/home/project/final_project`:

```bash
cp evidencias/2a_emotion_detection emotion_detection.py
python3
```
```python
>>> from emotion_detection import emotion_detector
>>> print(emotion_detector('I am really mad about this'))
>>> exit()
```
```bash
python3 test_emotion_detection.py
```
Copia toda la salida (incluido el prompt con la ruta) y pégala. Guárdala también como `2b_application_creation`.

## Pregunta 4 – Tarea 3, Actividad 1 (código)
Copia y pega el contenido de `evidencias/3a_output_formatting`.

## Pregunta 5 – Tarea 3, Actividad 2 (salida de terminal)
```bash
cp evidencias/3a_output_formatting emotion_detection.py
python3 -c "from emotion_detection import emotion_detector; print(emotion_detector('I love this new technology'))"
rm emotion_detection.py
```
La salida debe ser un diccionario con anger, disgust, fear, joy, sadness y `dominant_emotion`. Guárdala como `3b_formatted_output_test`.
(El `rm` del final borra la copia temporal de la raíz; el código bueno vive en el paquete.)

## Pregunta 6 – Tarea 4, Actividad 1 (URL)
`https://github.com/Andriuxone/oaqjp-final-project-emb-ai/blob/main/EmotionDetection/__init__.py`

## Pregunta 7 – Tarea 4, Actividad 2 (salida de terminal)
```bash
python3 -c "from EmotionDetection.emotion_detection import emotion_detector; print(emotion_detector('I am very angry'))"
```
Pega el comando y su resultado. Debe verse `'dominant_emotion': 'anger'`. Guárdalo como `4b_packaging_test`.

## Pregunta 8 – Tarea 5, Actividad 1 (código)
Copia y pega `test_emotion_detection.py`.

## Pregunta 9 – Tarea 5, Actividad 2 (salida de terminal)
```bash
python3 test_emotion_detection.py
```
Debe terminar con `Ran 1 test ... OK`. Guárdalo como `5b_unit_testing_result`.

## Pregunta 10 – Tarea 6, Actividad 1 (código)
Copia y pega el contenido de `evidencias/6a_server` (la versión de server.py antes del manejo de errores).

## Pregunta 11 – Tarea 6, Actividad 2 (captura `6b_deployment_test.png`)
```bash
python3 server.py
```
En **Skills Network Toolbox → Launch Application**, escribe el puerto **5000** y abre la app. Escribe por ejemplo `I think I am having fun`, pulsa **Run Sentiment Analysis** y toma una captura donde se vean el texto y la respuesta (por ejemplo, `... The dominant emotion is joy.`). Guárdala como `6b_deployment_test.png`.

## Pregunta 12 – Tarea 7, Actividad 1 (código)
Copia y pega el contenido de `evidencias/7a_error_handling_function`. Es `EmotionDetection/emotion_detection.py` con el caso `status_code == 400`.

## Pregunta 13 – Tarea 7, Actividad 2 (código)
Copia y pega el contenido de `evidencias/7b_error_handling_server` (server.py con `if response['dominant_emotion'] is None`).

## Pregunta 14 – Tarea 7, Actividad 3 (captura `7c_error_handling_interface.png`)
Con `python3 server.py` en marcha, deja el campo de texto **vacío** y pulsa el botón. Debe aparecer `Invalid text! Please try again!`. Toma la captura y guárdala como `7c_error_handling_interface.png`.

## Pregunta 15 – Tarea 8, Actividad 1 (código)
Copia y pega el contenido de `evidencias/8a_server_modified` (server.py final, con docstrings y listo para pylint).

## Pregunta 16 – Tarea 8, Actividad 2 (salida de terminal)
Detén el servidor con Ctrl+C y ejecuta:
```bash
pylint server.py
```
Debe salir `Your code has been rated at 10.00/10`. Pega la salida y guárdala como `8b_static_code_analysis`.

---

### Opcional: subir también las evidencias de terminal al repo
```bash
git add evidencias && git commit -m "Evidencias de terminal" && git push
```

---

# Versión con CAPTURAS DE PANTALLA (16 imágenes)

Toma todas las capturas en el laboratorio de IBM, en este orden. En las capturas de **código**, el archivo debe estar abierto en el editor con su nombre visible en la pestaña y el explorador de archivos a la izquierda. En las de **terminal**, debe verse el prompt con `/home/project/final_project`.

Preparación (si no lo hiciste ya):
```bash
cd /home/project
git clone https://github.com/Andriuxone/oaqjp-final-project-emb-ai.git final_project
cd final_project
python3 -m pip install requests flask pylint
```

| # | Archivo de captura | Qué debe verse |
|---|---|---|
| 1 | `1_folder_structure.png` | Explorador del IDE con `final_project` desplegado: `EmotionDetection/`, `static/`, `templates/`, `server.py`, `test_emotion_detection.py`, `README.md`. Mejor si además se ve en la terminal la salida de `ls -R` o `git clone`. |
| 2 | `2a_emotion_detection.png` | `emotion_detection.py` (raíz) abierto con el código de la Tarea 2 (devuelve `response.text`). |
| 3 | `2b_application_creation.png` | Terminal: `python3`, `from emotion_detection import emotion_detector`, `print(emotion_detector('I am really mad about this'))` con el JSON de respuesta, sin errores. |
| 4 | `3a_output_formatting.png` | `emotion_detection.py` (raíz) con el código de la Tarea 3 (json.loads, 5 emociones, `dominant_emotion`). |
| 5 | `3b_formatted_output_test.png` | Terminal con el diccionario `{'anger': ..., 'disgust': ..., 'fear': ..., 'joy': ..., 'sadness': ..., 'dominant_emotion': ...}`. |
| 6 | `4a_packaging.png` | Explorador con `EmotionDetection/` desplegado (`__init__.py` y `emotion_detection.py`) y `__init__.py` abierto, mostrando `from . import emotion_detection`. |
| 7 | `4b_packaging_test.png` | Terminal: `from EmotionDetection.emotion_detection import emotion_detector` y el resultado con `'dominant_emotion': 'anger'`. |
| 8 | `5a_unit_testing.png` | `test_emotion_detection.py` abierto con las 5 pruebas. |
| 9 | `5b_unit_testing_result.png` | Terminal: `python3 test_emotion_detection.py` → `Ran 1 test ... OK`. |
| 10 | `6a_server.png` | `server.py` abierto con la versión de la Tarea 6 (sin manejo de errores). |
| 11 | `6b_deployment_test.png` | Navegador con la app: texto escrito en el campo y la respuesta con las emociones y la emoción dominante. |
| 12 | `7a_error_handling_function.png` | `EmotionDetection/emotion_detection.py` abierto, con el bloque `if response.status_code == 400:` visible. |
| 13 | `7b_error_handling_server.png` | `server.py` final abierto, con `if response['dominant_emotion'] is None:` visible. |
| 14 | `7c_error_handling_interface.png` | App en el navegador con el campo vacío y la respuesta `Invalid text! Please try again!`. |
| 15 | `8a_server_modified.png` | `server.py` final completo (docstrings incluidos). |
| 16 | `8b_static_code_analysis.png` | Terminal: `pylint server.py` → `Your code has been rated at 10.00/10`. |

## Secuencia de comandos para las capturas

**Captura 1:** abre el explorador y ejecuta `ls -R | grep -v pycache` → captura.

**Capturas 2 y 3 (Tarea 2):**
```bash
cp evidencias/2a_emotion_detection emotion_detection.py
```
Abre `emotion_detection.py` → captura 2. Luego:
```bash
python3
>>> from emotion_detection import emotion_detector
>>> print(emotion_detector('I am really mad about this'))
>>> exit()
```
→ captura 3.

**Capturas 4 y 5 (Tarea 3):**
```bash
cp evidencias/3a_output_formatting emotion_detection.py
```
Abre/recarga `emotion_detection.py` → captura 4. Luego:
```bash
python3 -c "from emotion_detection import emotion_detector; print(emotion_detector('I love this new technology'))"
```
→ captura 5. Después borra la copia temporal: `rm emotion_detection.py`

**Capturas 6 y 7 (Tarea 4):** abre `EmotionDetection/__init__.py` → captura 6. Luego:
```bash
python3 -c "from EmotionDetection.emotion_detection import emotion_detector; print(emotion_detector('I am very angry'))"
```
→ captura 7.

**Capturas 8 y 9 (Tarea 5):** abre `test_emotion_detection.py` → captura 8. `python3 test_emotion_detection.py` → captura 9.

**Capturas 10 y 11 (Tarea 6):**
```bash
cp evidencias/6a_server server.py
```
Abre `server.py` → captura 10. Luego `python3 server.py`, Skills Network Toolbox → Launch Application → puerto 5000. Escribe `I think I am having fun` → **Run Sentiment Analysis** → captura 11. Detén con Ctrl+C.

**Capturas 12, 13 y 14 (Tarea 7):**
```bash
git checkout server.py
```
(Restaura el `server.py` final.) Abre `EmotionDetection/emotion_detection.py` → captura 12. Abre `server.py` → captura 13. `python3 server.py`, abre la app, deja el campo vacío y pulsa el botón → captura 14. Ctrl+C.

**Capturas 15 y 16 (Tarea 8):** con `server.py` abierto → captura 15. `pylint server.py` → captura 16.

Al final, `git status` debe decir que no hay cambios (salvo las capturas o archivos que agregues).
