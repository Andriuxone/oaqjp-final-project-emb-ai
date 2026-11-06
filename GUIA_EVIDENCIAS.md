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
