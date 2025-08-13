# Protocolo Operativo — Kinect + TouchDesigner + Ableton Live

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
  - Fondo con **pared lisa** (sin objetos brillantes o espejos).

### Software (preinstalado y probado)
- **TouchDesigner** (proyecto `Juntarse espacio reducido.toe`).
- **Ableton Live** (proyecto `Sonidos.als`).
- **Drivers Kinect**:
  - Si el sensor ya funciona en la notebook, no reinstalar; solo verificar conexión.

---

## 2) Preparación del espacio
1. **Despejar** totalmente el área de juego (retirar objetos y personas que no participen).
2. Fondo: **pared lisa** y uniforme.
3. **Iluminación**: pareja y difusa, sin contraluces ni luz directa a la cámara.
4. Colocar la Kinect a **75 cm de altura**.
5. Marcar la zona de juego: **entre 1,0 m y 3,5 m** desde el sensor (óptimo: 2,0–2,5 m).
6. Orientar la Kinect hacia el centro de la zona de juego, con inclinación leve (**0–10°**) hacia el torso de los jugadores.

---

## 3) Conexión y encendido
1. Conectar la Kinect a la **electricidad** y luego al **USB** de la notebook.
2. Conectar la notebook y equipos de audio a la red eléctrica.
3. Esperar que el sistema reconozca la Kinect (sin luces de error en adaptador).
4. Conectar los dispositivos de audio (parlantes o auriculares).

---

## 4) Inicio de software
1. Abrir **TouchDesigner** y cargar `Juntarse espacio reducido.toe`.
2. **Ableton Live** debería iniciarse automáticamente con `Sonidos.als`.  
   - Si no se abre, iniciarlo manualmente y cargar el proyecto.

---

## 5) Configuración en Ableton Live
1. En Ableton, cargar el set del show.
2. Cambiar de vista para ver las pistas de audio (referencia: *Imagen 2*).
3. Presionar las teclas **1**, **2**, **3** o **4** para seleccionar el audio a usar.  
   - Si está reproduciendo, presionar **Barra espaciadora** para detenerlo.  
   - Ejemplo: presionar **3** debería mostrar la bandera indicada en *Imagen 3*.
4. Colocar el **volumen master en 0** antes de reproducir (*Imagen 1*).

---

## 6) Verificación antes de comenzar
### Kinect en TouchDesigner
- Localizar nodos **Kinect CHOP** y **Kinect TOP**:
  - **CHOP**: mostrar variables en movimiento si un jugador es detectado.
  - **TOP**: mostrar imagen en tiempo real.

### Configuración de rutas de grabación
1. En TouchDesigner, ir a:
   - `field COMP field_parejas`
   - `field COMP field_condicion`
2. Estos nodos definen la carpeta de guardado.
3. Para modificar: presionar la **estrella inferior derecha** (*Imagen 9*).
4. Cambiar nombres siguiendo la nomenclatura:
   - Ej.: `Pareja1`, `Pareja2` (P mayúscula, resto minúscula).
   - Ej.: `condicion1` (sin tilde ni espacios).

### Audio en Ableton
- Confirmar que el set está listo y el botón **Play** funciona.

---

## 7) Ejecución — Inicio de juego y grabación
1. En **Ableton Live**:
   - Con master en **0**, presionar **Play**.
   - Ajustar volumen luego de verificar niveles.
2. En **TouchDesigner**:
   - Buscar el **CHOP Trigger** `GRABARR`.
   - Seleccionarlo (*Imagen 5*).
   - En **Parameters**, presionar botón **Pulse** junto a "Trigger" (*Imagen 6*).
3. Efectos esperados:
   - Inicio del juego.
   - Grabación de **video** (.mp4) y **datos** (.csv).
   - Verificación: valor `0 chan1` cambia momentáneamente a `1 chan`.

---

## 8) Durante la sesión
- Supervisar FPS y estabilidad de tracking.
- Verificar crecimiento del archivo de video y actualización del CSV.
- Mantener despejada la zona de juego.

---

## 9) Finalización de la sesión
1. En TouchDesigner, pulsar `PAUSARR` (mismo procedimiento que `GRABARR`).
2. En Ableton, detener reproducción.
3. Verificar archivos:
   - Reproducir unos segundos del video.
   - Abrir CSV para confirmar datos.
4. Guardar y respaldar:
   - Renombrar carpeta con fecha y copiar a backup.
5. Cerrar Ableton y TouchDesigner.
6. Apagar y desconectar equipos.

---

## 10) Solución de problemas rápida
- **Kinect sin señal**:
  1. Revisar alimentación y USB 3.0.
  2. Cambiar puerto.
  3. Reiniciar TouchDesigner.
  4. Reiniciar notebook.
  5. Revisar drivers.
- **Video no graba**:
  - Revisar `Movie File Out TOP` → File, Codec y parámetro Record.
  - Verificar carpeta y espacio en disco.
- **Datos no guardan**:
  - Revisar nodos de File Out DAT/CHOP, permisos de carpeta.
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
- Usar indicadores visuales del proyecto para confirmar estados (ej.: “REC”).
- La automatización de inicio/detención de Ableton vía OSC/MIDI es posible pero no incluida en este protocolo.



---

### Notas finales

* Si el proyecto tiene paneles/indicadores específicos (p.ej., “REC”, contadores, luces), usalos para confirmar estado.
* Si necesitás que `inicio` también arranque Ableton o que `FIN` lo detenga, se puede automatizar vía **OSC/MIDI** o **system commands** en TD (no incluido en este protocolo por depender del set actual).
