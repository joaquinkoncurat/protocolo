# Protocolo paso a paso

**Sistema:** Kinect + TouchDesigner + Ableton Live
**Proyecto TD:** `Lectura de datos nuevo del cuerpo.toe`

---

## 1) Requisitos previos

### Hardware

* Notebook (recom.: puerto **USB 3.0** libre para Kinect; evitar hubs USB).
* **Kinect** (v1, v2 o Azure) con **fuente de alimentación** y **cable USB**.
* Soporte o mesa para el sensor (altura **aprox. 75 cm** — altura estándar de mesa).
* Zapatilla eléctrica y alargues si hacen falta.
* Espacio despejado frente al sensor (ideal **3 × 3 m** con fondo de **pared lisa**).

### Software (instalado y probado previamente)

* **TouchDesigner** (proyecto: `Lectura de datos nuevo del cuerpo.toe`).
* **Ableton Live** (proyecto “Archivo de Ableton” del show/juego).
* **Drivers del Kinect** según modelo (Kinect v1: SDK 1.8; Kinect v2: SDK 2.0; Azure Kinect: SDK correspondiente).
  *Nota:* Si ya funciona en esta notebook, no es necesario reinstalar; solo verificar conexión.

---

## 2) Preparación del espacio

1. **Despejar** completamente el área frente a la Kinect. Dejar solo a las personas que van a jugar.

   * Evitar **objetos** que se muevan, espejos, vidrios y superficies brillantes.
2. **Fondo**: preferir una **pared lisa** y uniforme.
3. **Iluminación**: pareja/difusa, sin contraluces fuertes ni foco directo a la cámara.
4. **Altura del sensor**: colocar la Kinect a **\~75 cm** del piso (altura estándar de mesa).
5. **Distancia de trabajo**: marcar una zona de juego entre un máximo de **0,75 m y 3,5 m** del sensor .
6. **Orientación** del sensor: apuntar al centro de la zona de juego; si hace falta, **inclinación leve (0–10°)** hacia el torso de les participantes (hacia arriba).

---

## 3) Conexión y encendido

1. Conectar la **Kinect a la electricidad** (si tu modelo requiere fuente) y luego al **USB 3.0** de la notebook.
2. Conectar la notebook y el resto de aparatos a la red eléctrica.
3. Esperar unos segundos a que el sistema reconozca el dispositivo (sin luces de error en el adaptador, si aplica).

---

## 4) Inicio de software

1. Abrir **TouchDesigner** y cargar el archivo: `Lectura de datos nuevo del cuerpo.toe`.
2. **Ableton Live** debería iniciarse automáticamente.

   * Si **no** se abre: iniciar **Ableton Live** manualmente y cargar el **“Archivo de Ableton”** correspondiente.
3. En **Ableton**, ir al set/música del show. **Recomendación:** colocar el **volumen master en 0** antes de reproducir.
4. Aclarar mas y agragar imagenes de como reproducir y como bajar el volumen

---

## 5) Verificación rápida antes de comenzar

1. **Kinect en TouchDesigner**: ubicar los nodos del sensor (*Kinect CHOP/TOP)*.

   * Confirmar que hay **imagen** y/o **tracking** (esqueleto/manos) en el viewer.
   * Chequear tasa de cuadros (FPS) estable (\~30 FPS según modelo).
2. **Rutas de grabación**:

   * **Video**: localizar el **Movie File Out TOP** (o nodo equivalente) y verificar **ruta de archivo** y que la **carpeta exista**.
   * **Datos**: localizar el nodo de volcado (**File Out DAT/CHOP**, **Record DAT/CHOP** o equivalente) y verificar **ruta** y **formato** (CSV/TSV).
   * Si el proyecto usa un nombre de sesión, fijarlo (por ej., `YYYY-MM-DD_HHMM_SesionX`).
3. **Audio/Música**: en Ableton, verificar que el **set** esté listo y el **Play** funcione.

---

## 6) Ejecución — Inicio del juego y grabación

1. En **Ableton Live**: con el **volumen master en 0**, presionar **Play** en la música del show. (explicar mas esto)

   * Ajustar el volumen a gusto **luego** de verificar niveles.
2. En **TouchDesigner**: buscar el **CHOP Trigger** llamado `inicio`.

   * Seleccionar el nodo `inicio` y, en el panel de **Parameters**, presionar el botón **Pulse** del parámetro **Trigger** (o el botón/ícono de pulso que tenga el nodo).
   * Alternativa: si el `inicio` está conectado a un **Button COMP**, hacer **click** en el botón.
3. **Efecto esperado** al disparar `inicio`:

   * Se **inicia el juego**.
   * Comienza la **grabación de video** (Movie File Out en modo Record) y el **log de datos** (CSV/CHOP/DAT según corresponda).
   * Algún **indicador** en pantalla/TD debería pasar a **“REC”** o similar (según cómo esté diseñado el proyecto).

---

## 7) Durante la sesión

* Supervisar que **FPS** y **tracking** se mantengan estables.
* Verificar que el **archivo de video** vaya creciendo en la carpeta y que el **log de datos** se esté actualizando (si el proyecto escribe en caliente).
* Mantener despejada la **zona de juego**.

---

## 8) Finalización de la sesión

1. En **TouchDesigner**: buscar el **CHOP Trigger** llamado `FIN` y **pulsarlo** (mismo procedimiento que con `inicio`).

   * **Efecto esperado**: se **detiene** el juego y la **grabación** de video/datos.
2. En **Ableton Live**: **Stop** si no se detuvo automáticamente.
3. **Verificar archivos**:

   * Reproducir **unos segundos** del **video** grabado.
   * Abrir el **CSV/TSV** o archivo de datos y confirmar que tiene contenido.
4. **Guardar/Respaldar**: si el proyecto genera carpeta de sesión, **renombrar** con fecha y **copiar** a respaldo si corresponde.
5. **Cerrar** Ableton y TouchDesigner.
6. **Apagar**/desconectar la Kinect y equipos.

---

## 9) Checklist rápido (pre–post)

**Antes de iniciar**

*

**Para comenzar**

*

**Para finalizar**

*

---

## 10) Solución de problemas (rápido)

* **Kinect no aparece / sin tracking**:

  1. Revisar **alimentación** y **USB 3.0** directo; 2) Cambiar de puerto; 3) Cerrar y reabrir TD; 4) Reiniciar la notebook; 5) Verificar **drivers** del modelo.
* **El video no graba**:
  Abrir el **Movie File Out TOP** → chequear **File**, **Type/Codec** y que el **parámetro Record** esté **On** cuando se dispara `inicio`. Verificar que la **carpeta exista** y haya espacio en disco.
* **Datos no se guardan**:
  Revisar el nodo de **File Out/Record (DAT/CHOP)**: ruta, modo **Append/Overwrite**, permisos de carpeta.
* **Sonido muy alto**:
  Siempre poner **master en 0** antes de **Play** y subir gradualmente.
* **FPS bajo / tracking inestable**:
  Mejorar iluminación difusa, reducir apps abiertas, mantener distancia **2–2,5 m**, evitar sombras fuertes y elementos móviles en escena.

---

## 11) Parámetros de referencia

* **Altura de la Kinect**: **≈ 75 cm** (altura típica de mesa).
* **Distancia de juego**: **1,0 a 3,5 m** (óptimo **2,0–2,5 m**).
* **Inclinación**: **0–10°** hacia el torso si hace falta.
* **Zona despejada sugerida**: **3 × 3 m**.

---

### Notas finales

* Si el proyecto tiene paneles/indicadores específicos (p.ej., “REC”, contadores, luces), usalos para confirmar estado.
* Si necesitás que `inicio` también arranque Ableton o que `FIN` lo detenga, se puede automatizar vía **OSC/MIDI** o **system commands** en TD (no incluido en este protocolo por depender del set actual).
