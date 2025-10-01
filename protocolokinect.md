# Protocolo Operativo — Kinect + TouchDesigner + Ableton Live

**Sistema:** Kinect + TouchDesigner + Ableton Live  
**Proyecto TouchDesigner:** `Juntarse espacio reducido.toe`, `Juntarse espacio completo.toe`, `Juntarse espacio reducido ruido blanco de fondo.toe`, `Juntarse espacio completo ruido blanco de fondo.toe`.
*(ambos funcionan de manera idéntica, pero utilizan variables diferentes)*
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
- **TouchDesigner** con los proyectos: `Juntarse espacio reducido.toe`, `Juntarse espacio completo.toe`, `Juntarse espacio reducido ruido blanco de fondo.toe`, `Juntarse espacio completo ruido blanco de fondo.toe`.
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

> **Consejo:** Para saber si la Kinect esta conectada adecuadamente con la Notebook, al iniciar al programa `Juntarse espacio reducido.toe` o `Juntarse espacio completo.toe` en TouchDesigner automaicamente deberías ver de fondo la imagen que toma la Kinect.

---

## 4) Inicio de software
  - 1. Abrir **TouchDesigner**
    - Elegir cuál de los dos proyectos usar según corresponda:
      - `Juntarse espacio reducido.toe`
      - `Juntarse espacio completo.toe`
  - 2. **Ableton Live** debería iniciarse automáticamente con `Sonidos.als`.  
     - Si no se abre, iniciarlo manualmente y cargar el proyecto.

---

## 5) Configuración en Ableton Live
### Introducción
En Ableton existen dos tipos de vistas: Arrangement y Session.
[Imagen Arrangement](imgTutorial1.jpg) y [Imagen Session](imgTutorial2.jpg)

  - 1. En Ableton, cargar el set del show.
  **Vista Arragement:**
  - 2. Ir a la vista Arragement para ver las pistas de audio. [Ver imagen 3](imgTutorial3.jpg).
  - 3. Presionar la tecla **1** para seleccionar el audio. [Ver imagen 4](imgTutorial4.jpg).
     - Si está reproduciendo, presionar **Barra espaciadora** para detenerlo.
**Vista Session:**
  - 4. Colocar el **volumen master en 0** antes de reproducir [Imagen bajar volumen](imgTutorial5.jpg).
  - 5. Para los proyectos `Juntarse espacio reducido.toe`, `Juntarse espacio completo.toe` desactivar la pista del espacio (ruido blanco). Recomendación: poner en play la música, y se debería visualizar gris como la imagen (no se debería escuchar). [Ver imagen 17](imgTutorial17.jpg).
  - 6. Para los proyectos `Juntarse espacio reducido ruido blanco de fondo.toe`, `Juntarse espacio completo ruido blanco de fondo.toe` activar la pista del espacio (ruido blanco). Recomendación: poner play la música, y se debería visualizar verde como la imagen (se debería escuchar) [Ver imagen 18](imgTutorial18.jpg).
---

## 6) Verificación antes de comenzar
### Kinect en TouchDesigner
- Localizar nodos **Kinect CHOP** y **Kinect TOP** para ver si la Kinect está conectada con TouchDesigner [Ver imagen 6](imgTutorial6.jpg):
  - **CHOP**: al acercarce debería mostrar las variables de los jugadores en pantalla.
  - **TOP**: debería mostrar imagen en tiempo real.

> **Consejo:** Si al iniciar un programa (por ejemplo: `Juntarse espacio reducido.toe`) se ve de fondo lo que la cámara de la Kinect graba, ya está funcionando correctamente la conexión.

### Configuración de rutas de grabación (se realiza de la misma forma en todos los programas):
  - 1. En TouchDesigner, ir a [Ver imagen 7](imgTutorial7.jpg):
   - `field COMP field_parejas`
   - `field COMP field_condicion`
  - 2. Estos nodos definen el nombre de la carpeta de guardado con este formato: "/Pareja1/Condicion1/Repeticion1/video.mp4".
  - 3. Para modificar el nombre de la carpeta: presionar la **estrella inferior derecha** en field_pareja y/o field_condicion [Ver imagen 8](imgTutorial8.jpg).
  - 4. Al presionar la estrella inferior derecha, podes modificar el contenido. [Ver imagen 9](imgTutorial9.jpg) 
  - 5. Cambiar nombres siguiendo la nomenclatura:
   - Ej.: `Pareja1`, `Pareja2` (P mayúscula, resto minúscula, y terminando con el número de la pareja).
   - Ej.: `Condicion1`, `Condicion2` (C mayúscula, resto minúscula, sin tilde en la 'o', y terminando con el número de la condición).
  - 6. Se propone dejar ya las condiciones con cada proyecto:
  Condicion1: `Juntarse espacio reducido.toe`.
  Condicion2: `Juntarse espacio completo.toe`.
  Condicion3: `Juntarse espacio reducido ruido blanco de fondo.toe`.
  Condicion4: `Juntarse espacio completo ruido blanco de fondo.toe`.

> **Nota:** El nombre de la carpeta `repeticion` no se anota manualmente, se hace automáticamente. Si no existe ninguna prueba, se crea `Repeticion1`. Si ya existen repeticiones previas, se crea la siguiente disponible.


### Audio en Ableton
- Por último, verificar que el set de Ableton está listo.
- En la vista Arragement, presionar el botón **Play** o la barra espaciadora para iniciar la música.

> **Nota:** Al darle play o iniciar la música, no se deberia escuchar el sonido (el volumen debe estar bajado como se ve en el punto 5.4).

---

## 7) Ejecución — Inicio de juego y grabación
  - 1. En **Ableton Live**:
   - En la vista Arragement, presionar el botón **Play** o la barra espaciadora para iniciar la música.
  - 2. En **TouchDesigner**:
   - Buscar el **CHOP Trigger** `GRABARR` [Ver imagen 10](imgTutorial10.jpg).
   - Hacer clic izquierdo para seleccionarlo.
   - En **Parameters** (ventana con información que se encuentra en la esquina superior derecha), presionar botón **Pulse** junto a "Trigger Pulse" [Ver imagen 11](imgTutorial11.jpg).
   - En este momento inicia la grabación de datos y video.
    
  - 3. Efectos esperados:
   - Inicio del juego.
   - Grabación de **video** (.mp4) y **datos** (.csv).
   - Verificación: valor `0 chan1` cambia momentáneamente a `1 chan` [Ver imagen 12](imgTutorial12.jpg).
  
> **Consejo:** Mientras está en ejecución, se puede observar que el nodo `script2` se conecta con distintos nodos del sistema [Ver imagen 13](imgTutorial13.jpg)

---

## 8) Durante la sesión se puede
- Verificar la creación de la ruta de guardado.
- Verificar el crecimiento del archivo de video y actualización del CSV.

---

## 9) Finalización de la sesión
  - 1. En TouchDesigner, pulsar `PAUSARR` (mismo procedimiento que `GRABARR`).
    - Buscar el **CHOP Trigger** `PAUSARR` [Ver imagen 14](imgTutorial14.jpg).
    - Hacer clic izquierdo para seleccionarlo.
    - En **Parameters** (ventana con información que se encuentra en la esquina superior derecha), presionar botón **Pulse** junto a "Trigger Pulse" [Ver imagen 15](imgTutorial15.jpg).
    - En este momento finaliza la grabación de datos y video.
  - 2. En Ableton, detener reproducción.
    - Ir a la vista de Arrangement y pulsar la barra espaciadora o presionar pausa [Ver imagen 16](imgTutorial16.jpg).  
  - 3. Verificar archivos:
   - Reproducir unos segundos del video.
   - Abrir CSV para confirmar datos.

> **Nota:** Si se va a grabar otra repetición, continuar con el paso 10.

  - 4. Cerrar Ableton y TouchDesigner.
  - 5. Apagar y desconectar equipos.

---

## 10) Iniciar nueva repetición
- Si se quiere realizar otra repetición con el **mismo proyecto de TouchDesigner**: volver al punto  5) Configuración en Ableton Live. Y luego:
    - Si es la misma pareja y condición, ir al punto 7)  Ejecución — Inicio de juego y grabación
    - Si se cambia la pareja o condición, volver al punto 6) Verificación antes de comenzar
- Si se desea **cambiar de proyecto de TouchDesigner** (ejemplo: pasar de `Juntarse espacio reducido.toe` a `Juntarse espacio completo.toe`):
    - Cerrar el proyecto actual en TouchDesigner.
    - Abrir el otro proyecto (`.toe`).
    - Verificar nuevamente la conexion con Kinect (punto 6).
    - Luego continuar desde el punto 5) Configuración de Ableton Live

> **Nota:** Al cambiar de proyecto de TouchDesigner no es necesario cambiar el proyecto de Ableton Live aunque te lo pida (te va a pedir cerrar el proyecto de Ableton Live abierto actualmente para abrir el mismo, recomiendo poner en cancelar y continuar). Se recomienda mantener abierto `Sonidos.als` durante toda la sesión.

---

### Aclaraciones finales
- Si el programa se detiene o sucede algún error durante la grabación, los archivos se guardan igualmente.
- Todos los proyectos funcionan exactamente igual, solo cambian las variables internas.
- Todos los proyectos utilizan el mismo proyecto de Ableton Live (`Sonidos.als`).
