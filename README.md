![Logo Institucional](https://github.com/JonatanBogadoUNLZ/PPS-Jonatan-Bogado/blob/9952aac097aca83a1aadfc26679fc7ec57369d82/LOGO%20AZUL%20HORIZONTAL%20-%20fondo%20transparente.png)


---

## 📛 Naming del repositorio (OBLIGATORIO)

El nombre del repositorio debe seguir este esquema:

**`ANIO_CUATRIMESTRE_TIPO_PROYECTO_APELLIDOS`**

Donde:
- **ANIO**: año de cursada (ej. `2026`)
- **CUATRIMESTRE**: `1C` o `2C`
- **TIPO**: `PPS` o `PF` (Proyecto Final)
- **PROYECTO**: nombre corto *sin espacios* (recomendado: `kebab-case` o `CamelCase`)
- **APELLIDOS**: apellidos de integrantes separados por `_` (sin tildes, sin ñ)

✅ Ejemplos:
- `2026_1C_PPS_ComederoSmart_Salto_Vazquez`
- `2026_2C_PF_MecaChess_Duarte_Diaz`
- `2025_2C_PPS_Escaner3D_DalleRivePrieto_Labreniuk`

> Nota: GitHub **no permite** usar “/” en el nombre del repositorio.  
> Por eso se usa **TIPO = PPS o PF** como campo separado.

---

## 🧩 Cómo usar esta plantilla (estudiantes)

0) **Crear el repo con el nombre correcto (OBLIGATORIO)**  
   Esquema: `ANIO_CUATRIMESTRE_TIPO_PROYECTO_APELLIDOS`

1) Crear tu repositorio desde esta plantilla:
   - Opción A (recomendada): **Use this template** → Create a new repository  
   - Opción B: **Fork**

2) Editar este archivo `README.md` completando todos los campos `[ ... ]`.

3) Subir archivos a las carpetas correspondientes:
   - Código en `CODIGO/`
   - Planos y esquemas en `PLANOS/`
   - Fotos / videos en `MULTIMEDIA/`
   - Datasheets en `DATASHEET/`
   - Informes en `INFORMES/`

---

## ✅ Checklist de entrega
- [x] Naming correcto del repo: `ANIO_CUATRIMESTRE_TIPO_PROYECTO_APELLIDOS`
- [] Título, autores, materia, **tipo (PPS/PF)**, año y cuatrimestre completos
- [ ] Brief completo (one-liner + pitch + problema + solución + alcance + estado)
- [ ] Instrucciones de uso reproducibles (otro puede correrlo)
- [ ] Lista de componentes con cantidades y modelos
- [ ] Esquemáticos/planos adjuntos en `PLANOS/`
- [ ] Fotos / video demostración en `MULTIMEDIA/`
- [ ] Informe PDF en `INFORMES/` (si aplica)

---

# DOCK DE CARGA REMOTA 

**Tipo:** PPS
**Año:** 2026 — **Cuatrimestre:** 2C 

**Carrera:** Ingeniería Mecatrónica  
**Materia / Curso:** PRACTICAS PROFESIONALES SUPERVISADA 
**Docente / Cátedra:** CRISTIAN  LUKASZEWICZ
**Autor/es:** CHIMENTE MATIAS · RODRIGUEZ LOMAZZI BIANCA LUJAN

---

## Introducción / Objetivo

**Contexto (2–4 líneas):**  
El sistema de rehabilitación EMG para chicos de 5 a 10 años está formado por módulos de brazo (caja electrónica + manga con electrodos), un auto controlado por EMG y una app de juegos. 
La rehabilitación no termina en el consultorio: para que funcione, el chico tiene que practicar seguido, y eso pasa sobre todo en casa. Todo el equipo usa baterías LiPo, así que hace falta una forma simple, segura y ordenada de recargarlas y guardarlas entre sesiones.

**Problema a resolver:**  
Hoy la rehabilitación con EMG depende de ir al consultorio: el equipo, la carga de las baterías y el acceso a los ejercicios quedan a cargo del profesional, y el chico solo practica durante las sesiones presenciales. Eso limita cuánto puede entrenar y hace que la terapia sea igual para todos, cuando cada chico avanza a su propio ritmo. Para llevar la rehabilitación a casa hace falta una base sencilla que mantenga los módulos y el auto cargados y listos, y que dé acceso directo a la página donde están los ejercicios y el registro de progreso. Así la familia puede usar el sistema sin ayuda técnica y la terapia se adapta a cada chico.

**Objetivo general:**  
Diseñar y construir un dock de carga doméstico que cargue de forma eficiente y segura las baterías de los módulos EMG y del auto, y que sirva como punto de acceso simple a la página de la plataforma. Así el chico puede hacer sus sesiones en casa sin ir al consultorio, y la rehabilitación se puede individualizar según su progreso.


---

## Índice
- [Brief](#brief)
- [Descripción técnica](#descripción-técnica)
- [Arquitectura del sistema](#arquitectura-del-sistema)
- [Instrucciones de uso](#instrucciones-de-uso)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Listado de componentes](#listado-de-componentes)
- [Esquemáticos / Planos](#esquemáticos--planos)
- [Fotos / Videos](#fotos--videos)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Autor](#autor)
- [Licencia](#licencia)

---

## Brief

**One-liner (1 frase):**  
Base de carga doméstica que mantiene listos los módulos EMG y el auto del sistema de rehabilitación infantil, para que las familias hagan sesiones personalizadas en casa sin depender del consultorio.

**Elevator pitch (30 segundos):**  
Este proyecto Dock de carga Robrain Kids (tipo PPS, 2026, 2.º cuatrimestre) resuelve la dependencia del consultorio en la rehabilitación EMG infantil, que limita cuánto puede practicar el chico y hace que la terapia sea igual para todos, mediante una base que carga de forma segura y eficiente las baterías de los módulos y del auto y da acceso directo a la plataforma de ejercicios.
Está orientado a familias de chicos de 5 a 10 años en rehabilitación de miembro superior y permite tener el equipo siempre listo para usar, hacer más sesiones por semana en casa y adaptar los ejercicios al progreso de cada chico.
Se implementa con contactos pogo pin, módulos de carga LiPo con protección (TP4056), ESP32 con conexión BLE/WiFi, y una carcasa impresa en 3D.

### Problema
Contexto: hogar, como continuación de la rehabilitación EMG infantil que empieza en el consultorio.
Dolor principal: cada dispositivo usa su propia batería y hay que cargarla aparte, así que es fácil olvidarse de alguna o que esté descargada justo cuando toca la sesión. Tener todo en una sola base hace más simple dejar el equipo listo para usar en casa.
Impacto: si el equipo no está cargado se pierden sesiones y cuesta mantener la constancia de la terapia. Con el dock, las baterías se cargan de forma ordenada y segura, el chico puede practicar más seguido desde casa y los ejercicios se ajustan a su progreso.


## Solución propuesta

Qué hace (features):
Carga en un solo lugar las baterías del brazo con contactos pogo pin: solo hay que apoyar el dispositivo.
Avisa con una luz cuando cada batería terminó de cargar (indicador del TP4056).
Tiene una etiqueta NFC: con solo acercar el celular se abre la página de ejercicios, donde queda el registro de cada sesión.

Cómo lo hace (alto nivel): se apoya el dispositivo en el dock → los pogo pins hacen contacto con la batería → el módulo de carga con protección regula la carga → el LED indica cuándo terminó → se acerca el celular a la etiqueta NFC de la base y se abre directamente la página para arrancar la sesión.
Valor diferencial: junta la carga de todo el equipo en una base simple y ordenada, pensada para usar en casa sin conocimientos técnicos. Con el NFC, empezar una sesión es tan fácil como acercar el celular.

Alcance

Incluye:

Diseño e impresión 3D de la base con alojamiento para las cajas de la manga y el celular.
Circuito de carga con protección y contactos pogo pin para cada dispositivo.
Indicador LED de carga completa.
Etiqueta NFC en la base para abrir la página de ejercicios desde el celular.

No incluye (por ahora):

Indicador de porcentaje de batería: solo está la luz del TP4056 que avisa cuando termina la carga.
Monitoreo del estado de carga desde la app o la página.


### Estado del proyecto

Estado del proyecto
Madurez: MVP
Qué funciona hoy:
Carga de las baterías de los módulos y del auto con contactos pogo pin.
LED que indica cuándo termina la carga.
Apertura de la página de ejercicios acercando el celular a la etiqueta NFC.
Base impresa en 3D con lugar para todos los dispositivos.


### Demo rápida
- **Video / GIF:** [link o ruta en MULTIMEDIA]
- **Instrucciones express (2 minutos):**
1) Conectá el dock a la commputadora y apoyá los módulos, de forma que los pogo pins hagan contacto.
2) Esperá a que se encienda el LED de carga completa de cada dispositivo.
3) Acercá el celular a la etiqueta NFC de la base para abrir la página de ejercicios, colócate las mangas y empeza la sesión.

---

## Descripción técnica
Descripción técnica

El dock es una base de carga pasiva para todos los dispositivos del sistema de rehabilitación EMG: los módulos de brazo y el auto. La misma se alimenta por un cable USB que entrega 5V a 500 mA

Carga de baterías
Los dispositivos usan baterías LiPo. Para cada celda se usa un módulo TP4056 con protección: carga primero con corriente constante y después con tensión constante, hasta 4,2 V, y tiene protección contra sobrecarga, sobredescarga y cortocircuito. Cuando la carga termina, el LED del módulo cambia de estado. Ese es el indicador visual que ve el usuario. Elegimos el TP4056 porque es económico, fácil de conseguir y ya trae la protección, así que no hace falta un microcontrolador en la base.

Conexión por pogo pins
La energía pasa de la base a cada dispositivo por contactos pogo pin. Así no hay cables ni conectores que haya que enchufar: el chico o la familia solo apoyan el dispositivo en su lugar. Los pogo pins aguantan muchos ciclos de conexión sin desgastarse como un conector USB, y la forma de cada alojamiento en la base guía el dispositivo para que los contactos queden alineados y con la polaridad correcta.

Acceso por NFC
La base tiene una etiqueta NFC pasiva grabada con la URL de la página de ejercicios. Al acercar el celular, se abre la página automáticamente, sin buscar la dirección ni configurar nada. Como la etiqueta no necesita alimentación ni electrónica extra, mantiene el dock simple.

Diseño mecánico
La carcasa está impresa en 3D, con un alojamiento específico para cada módulo y para el auto, de modo que cada dispositivo tiene su lugar y el equipo queda ordenado. Se pensó para que la use un chico de 5 a 10 años: formas simples, sin partes chicas sueltas y con la electrónica cerrada dentro de la base.

Consideraciones

La corriente de carga del TP4056 se ajusta con su resistencia de programación, según la capacidad de cada batería, para no exigirla de más.
Hay que dejar ventilación en la carcasa, porque los módulos de carga levantan temperatura.
El indicador solo muestra si la carga terminó, no el porcentaje. Eso queda como mejora a futuro.

---

## Arquitectura del sistema

Entradas (sensores / señales):

Alimentación de 5 V por USB.
Detección de la batería: el TP4056 mide la tensión y la corriente de carga de cada celda.
Contacto físico del dispositivo con los pogo pins al apoyarlo en la base.

Procesamiento / Control:

Un módulo TP4056 con protección por dispositivo, que controla la carga en dos etapas (corriente constante y después tensión constante hasta 4,2 V) y corta ante sobrecarga, sobredescarga o cortocircuito.
No hay microcontrolador: el control lo resuelve el hardware de cada módulo de carga.

Salidas (actuadores / señales):

Corriente de carga hacia la batería de cada dispositivo, a través de los pogo pins.
LED indicador del TP4056 (cargando / carga completa).

Interfaz (si aplica):

Etiqueta NFC pasiva que, al acercar el celular, abre la página web de ejercicios donde queda el registro de cada sesión.


---

## Instrucciones de uso

### Requisitos previos
- **Software / IDE:** no hace falta, porque el dock no tiene firmware ni necesita programarse.
- **Drivers / librerías:** no hace falta ninguno. Solo se necesita un celular con NFC activado, navegador y conexión a internet para abrir la página de ejercicios.
- **Hardware mínimo:**
  - Fuente USB de 5 V con corriente suficiente para cargar todos los dispositivos a la vez (por ejemplo, 5 V / 2 A) y su cable.
  - Los módulos de brazo y el auto, con sus baterías colocadas.

Instalación / Puesta en marcha

1) Ubicá el dock sobre una superficie firme.
2) Conectá el dock a la fuente USB de 5 V con el cable.
3) Apoyá los módulos en la base, fijándote que los pogo pins hagan contacto. El LED del TP4056 de cada uno tiene que encenderse indicando que está cargando.
4) Para validar el funcionamiento, esperá a que cada LED cambie a carga completa. Después acercá el celular a la etiqueta NFC y fijate que se abra la página de ejercicios.

### Uso

- **Modo normal:** después de cada sesión, apoyá los módulos en el dock para que se carguen. Cuando el LED indica carga completa, el equipo está listo. Para empezar la sesión, retirá los dispositivos de la base y acercá el celular a la etiqueta NFC para abrir la página de ejercicios.
- **Calibración (si aplica):** el dock no necesita calibración. La calibración de la señal EMG de ambos brazos se hace desde la página web, al empezar la sesión, siguiendo los pasos que indica la misma página.
- **Notas:**
  - Usá siempre una fuente de 5 V adecuada.
  - Mantené limpios los pogo pins y los contactos de los dispositivos para que la conexión sea buena.
  - Si un LED no se enciende al apoyar un dispositivo, reacomodalo en su lugar hasta que los contactos queden alineados.
  - Conviene que un adulto supervise la carga y que el dock quede fuera del alcance de los más chicos mientras está enchufado.


---

## Tecnologías utilizadas

Robótica / Control: no aplica en el dock. El control de carga lo hace el hardware de los módulos TP4056, sin microcontrolador.
Electrónica: módulos de carga TP4056 con protección, baterías LiPo, contactos pogo pin, LEDs indicadores de carga, etiqueta NFC pasiva  y fuente USB de 5 V.
Programación: no aplica en el dock. La etiqueta NFC solo se graba una vez con la URL de la página de ejercicios.
Plataformas / Tools: diseño CAD e impresión 3D de la carcasa y una app de grabación NFC (por ejemplo, NFC Tools). La página web de ejercicios, que hace la calibración EMG y guarda el registro de las sesiones, está publicada en Netlify y se desarrolló con ayuda de Claude (Anthropic).
IA (si aplica): se usó Claude (Anthropic) como asistente para desarrollar la página web.

---

## Listado de componentes

Módulo de carga LiPo
Cantidad: 1 por dispositivo
Modelo: TP4056 con protección (DW01A + MOSFET)
Función: controla la carga de cada batería y la protege contra sobrecarga, sobredescarga y cortocircuito.

Contactos pogo pin
Cantidad: 4
Modelo: pogo pin con resorte
Función: transmiten la energía de carga sin cables ni conectores.

Etiqueta NFC
Cantidad: 1
Modelo: tag pasivo NTAG213/215 (NDEF)
Función: abre la página web de ejercicios al acercar el celular.

Fuente de alimentación
Cantidad: 1
Modelo: USB 5 V / 2 A
Función: alimenta el dock.

Cable USB
Cantidad: 1
Modelo: USB según la entrada del dock
Función: conecta la fuente con el dock.

Carcasa
Cantidad: 1
Modelo: impresa en 3D en PLA
Función: aloja la electrónica, guía cada dispositivo a su posición de carga y tiene un soporte para apoyar el celular.


---

## Esquemáticos / Planos
- [Plano/Esquemático 1] → `PLANOS/[archivo]`
- [Plano/Esquemático 2] → `PLANOS/[archivo]`

---

## Fotos / Videos
- Foto 1 → `MULTIMEDIA/[archivo]`
- Foto 2 → `MULTIMEDIA/[archivo]`
- Video demo → `MULTIMEDIA/[archivo]` o [link]

---

## Estructura del repositorio
- `CODIGO/` — Código fuente del proyecto.
- `MULTIMEDIA/` — Imágenes y videos.
- `PLANOS/` — Esquemáticos y diagramas.
- `DATASHEET/` — Hojas de datos y especificaciones.
- `INFORMES/` — Informes, Gantt, manuales, PDFs.

---

## Autor

**[CHIMENTE, MATIAS]** — [44709249]  
**[RODRIGUEZ LOMAZZI, BIANCA]** — [44650286]  

Contacto:

matias.chimente@gmail.com 
[LinkedIn](https://www.linkedin.com/in/matias-chimente/)

Biancalujan58@gmail.com 
[LinkedIn](https://www.linkedin.com/in/biancalomazzi/)


---

## Licencia
[Definir según la cátedra: MIT / uso académico / etc.]

---

## About (descripción corta del repositorio)

Usar este texto (o similar) en el campo **About** de GitHub:

**[PPS] — [DOCK DE CARGA REMOTA] — FI-UNLZ — [2026] [2C] — [CHIMENTE , RODRIGUEZ LOMAZZI ]**
