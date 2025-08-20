<img width="887" height="241" alt="image" src="https://github.com/user-attachments/assets/411c5603-96a2-41ca-9665-5b0f61c59985" /><img width="1009" height="431" alt="image" src="https://github.com/user-attachments/assets/f69d7f9e-fe65-4641-9760-eaf7b8b4c5fe" /># Protocolo Operativo — Kinect + TouchDesigner + Ableton Live

**Sistema:** Kinect + TouchDesigner + Ableton Live  
**Proyecto TouchDesigner:** `Juntarse espacio reducido.toe`  
**Proyecto Ableton Live:** `Sonidos.als`

---

## 1) Requisitos previos

### Hardware necesario
- **Notebook** (con TouchDesigner y Ableton Live instalados y funcionando).
- **Kinect** (modelo compatible con drivers instalados).
- **Soporte o mesa** para el sensor (altura recomendada: **aprox. 75 cm**).
- **Zapatilla eléctrica** y **alargues** si son necesarios.
- **Parlantes** o **auriculares** para monitorear el audio.
- **Espacio despejado** frente al sensor:
  - Ancho: **3 m**.
  - Fondo: **3 a 4 m** como mínimo.
  - Fondo con **pared lisa** (sin objetos brillantes, espejos, ventanas que entre luz, y minimizar los objetos como bancos o sillas).

### Software (preinstalado y probado)
- **TouchDesigner** (proyecto `Juntarse espacio reducido.toe`).
- **Ableton Live** (proyecto `Sonidos.als`).
- **Drivers Kinect**:
  - Si el sensor ya funciona en la notebook, no reinstalar; solo verificar conexión.

---

## 2) Preparación del espacio
  - 1. **Despejar** totalmente el área de juego (retirar objetos y personas que no participen).
  - 2. Fondo: **pared lisa** y uniforme.
  - 3. **Iluminación**: pareja y difusa, sin contraluces ni luz directa a la cámara.
  - 4. Colocar la Kinect a **75 cm de altura**.
  - 5. Marcar la zona de juego: **entre 1,0 m y 3,5 m** desde el sensor (óptimo: 2,0–2,5 m).
  - 6. Orientar la Kinect hacia el centro de la zona de juego, con inclinación leve (**0–10°**) hacia el torso de los jugadores.

---

## 3) Conexión y encendido
  - 1. Conectar la Kinect a la **electricidad** y luego al **USB** de la notebook.
  - 2. Conectar la notebook y equipos de audio a la red eléctrica.
  - 3. Esperar que el sistema reconozca la Kinect (sin luces de error en adaptador).
  - 4. Conectar los dispositivos de audio (parlantes o auriculares).

> **Consejo:** Para saber si la Kinect esta conectada adecuadamente con la Notebook, al iniciar al programa `Juntarse espacio reducido.toe`  de TouchDesigner automaticamente deberian ver de fondo la imagen que toma la Kinect.

---

## 4) Inicio de software
  - 1. Abrir **TouchDesigner** y cargar `Juntarse espacio reducido.toe`.
  - 2. **Ableton Live** debería iniciarse automáticamente con `Sonidos.als`.  
     - Si no se abre, iniciarlo manualmente y cargar el proyecto.

---

## 5) Configuración en Ableton Live
### Introducción
En Ableton existen dos tipos de vistas: Arrangement y Session.
[Imagen Arrangement](imgTutorial1.png) y [Imagen Session](imgTutorial2.png)
  - 1. En Ableton, cargar el set del show.
  Vista Arragement:
  - 2. Cambiar de vista para ver las pistas de audio [Ver imagen 3](imgTutorial3.png).
  - 3. Presionar las teclas **1**, **2**, **3** o **4** para seleccionar el audio a usar.
     - Si está reproduciendo, presionar **Barra espaciadora** para detenerlo.  
     - Ejemplo: presionar **3** debería mostrar la bandera indicada en [Ver imagen 2](imgTutorial2.png).
  Vista Session:
  - 4. Colocar el **volumen master en 0** antes de reproducir [Bajar volumen](imgTutorial3.png).

---

## 6) Verificación antes de comenzar
### Kinect en TouchDesigner
- Localizar nodos **Kinect CHOP** y **Kinect TOP** [Ver imagen 4](imgTutorial4.png):
  - **CHOP**: mostrar variables en movimiento si un jugador es detectado.
  - **TOP**: mostrar imagen en tiempo real.


### Configuración de rutas de grabación
  - 1. En TouchDesigner, ir a [Ver imagen 8](imgTutorial8.png):
   - `field COMP field_parejas`
   - `field COMP field_condicion`
  - 2. Estos nodos definen el nombre de la carpeta de guardado.
  - 3. Para modificar el nombre de la carpeta: presionar la **estrella inferior derecha** en field_pareja y/o field_condicion [Ver imagen 9](imgTutorial9.png).
  - 4. Al presionar la estrella inferior derecha, podes modificar el contenido. [Ver imagen 10](imgTutorial10.png) 
  - 5. Cambiar nombres siguiendo la nomenclatura:
   - Ej.: `Pareja1`, `Pareja2` (P mayúscula, resto minúscula, y terminando con el número de la pareja).
   - Ej.: `Condicion1`, `Condicion2` (C mayúscula, resto minúscula, sin tilde en la 'o', y terminando con el número de la condición).

### Audio en Ableton
- Por último, verigicar que el set de Ableton está listo.
- En la vista Arragement, presionar el botón **Play** o la barra espaciadora para iniciar la música.

> **Nota:** Al darle play o iniciar la música, no se deberia escuchar el sonido (deberia estar bajado como se ve en el punto " 5) 4. ").

---

## 7) Ejecución — Inicio de juego y grabación
  - 1. En **Ableton Live**:
   - En la vista Arragement, presionar el botón **Play** o la barra espaciadora para iniciar la música.

> **Nota:** Al darle play o iniciar la música, no se deberia escuchar el sonido (deberia estar bajado como se ve en el punto " 5) 4. ").

  - 2. En **TouchDesigner**:
   - Buscar el **CHOP Trigger** `GRABARR` [Ver imagen 5](imgTutorial5.png).
   - Hacer clic izquierdo para seleccionarlo.
   - En **Parameters** (ventana con información que se encuentra en la esquina superior derecha), presionar botón **Pulse** junto a "Trigger Pulse" [Ver imagen 12](imgTutorial12.png).
   - En este momento inicia la grabación de datos y video.
    
  - 3. Efectos esperados:
   - Inicio del juego.
   - Grabación de **video** (.mp4) y **datos** (.csv).
   - Verificación: valor `0 chan1` cambia momentáneamente a `1 chan` [Ver imagen 6](imgTutorial6.png).
  
> **Nota:** Mientras esta en ejecución el programa, se puede observar que el nodo script2 se conecta con distintos nodos del sistema   [Ver imagen 7](imgTutorial7.png)

---

## 8) Durante la sesión se puede
- Verificar crecimiento del archivo de video y actualización del CSV.
- Mantener despejada la zona de juego.

---

## 9) Finalización de la sesión
  - 1. En TouchDesigner, pulsar `PAUSARR` (mismo procedimiento que `GRABARR`).
    - Buscar el **CHOP Trigger** `GRABARR` [Ver imagen 14](imgTutorial14.png).
    - Hacer clic izquierdo para seleccionarlo.
    - En **Parameters** (ventana con información que se encuentra en la esquina superior derecha), presionar botón **Pulse** junto a "Trigger Pulse" [Ver imagen 13](imgTutorial13.png).
    - En este momento finaliza la grabación de datos y video.
  - 2. En Ableton, detener reproducción.
    - Ir a la vista de Arrangement y pulsar la barra espaciadora o presionar pausa [Ver imagen 15](imgTutorial15.png).  
  - 3. Verificar archivos:
   - Reproducir unos segundos del video.
   - Abrir CSV para confirmar datos.
  - 4. Cerrar Ableton y TouchDesigner.
  - 5. Apagar y desconectar equipos.

---

## 10) Solución de problemas rápida
- **Kinect sin señal**:
  1. Revisar alimentación y USB 3.0.
  2. Cambiar puerto.
  3. Reiniciar TouchDesigner.
  4. Reiniciar notebook.
- **Sonido alto**:
  - Siempre iniciar con master en 0 y subir gradualmente.
- **FPS bajo**:
  - Mejorar iluminación, cerrar otras apps, mantener distancia óptima.

---

## 11) Parámetros de referencia
- Altura Kinect: **75 cm**.
- Distancia de juego: **1,0 – 3,5 m** (óptimo: 2,0–2,5 m).
- Inclinación: **0–10°** hacia torso.
- Zona despejada: **3 × 3 m**.

---

### Notas finales
- Si el programa se detiene o sucede algo durante la grabación, los archivos se guardan igualmente.
