# Apuntes a mano de clase (carpeta FOTOS)

> Transcripción y organización de las fotos de apuntes manuscritos enviadas por WhatsApp.
> Autor: Jaime Landazuri · Sistema embebido: Sistemas Digitales · Unidad 1 · UNL

Directorio fuente: `FOTOS/` (5 imágenes JPEG).

## Índice

| # | Foto | Tema dominante | Semana relacionada |
|---|---|---|---|
| 1 | `WhatsApp Image 2026-11-09 at 21.35.34.jpeg` | Microcontrolador = CPU + memoria + periféricos; buses; reloj | 1 |
| 2 | `WhatsApp Image 2026-11-09 at 21.35.34 (1).jpeg` | Arquitecturas Harvard–Von Neumann; tipos de memoria y ciclos; comparativa ATmega328P vs ESP32; conversión bin/dec/hex | 1 → 2 (puente) |
| 3 | `WhatsApp Image 2026-11-09 at 21.35.34 (2).jpeg` | DDRB/PORTB/PINB; alta impedancia; manipulación de bits | 1 |
| 4 | `WhatsApp Image 2026-11-09 at 21.35.34 (3).jpeg` | AVR vs ESP32; UART; GPIO matrix | 2 |
| 5 | `WhatsApp Image 2026-11-09 at 21.35.35.jpeg` | Temporizadores: prescaler, resolución, `Tiempo = alarma × resolución`; ISR | 3 (puente a 4) |

## Foto 1 · Definición de microcontrolador y sus buses

> **Microcontroladores**
> Los microcontroladores incluyen CPU, memoria y periféricos en un solo chip. Todos estos componentes se comunican usando buses, que transportan bits en serie o paralelo; estos bits están almacenados en memoria a nivel de componentes llamados flip-flops. El reloj del sistema coordina las acciones de los componentes del chip. Acciones como: operaciones aritméticas, lecturas, escrituras, entrada de dispositivos, etc.

Enlaza con: Semana1_P1.md (bloques del MCU, tres buses).

## Foto 2 · Arquitecturas, memorias y comparativa

Columna izquierda — **Arquitecturas**: Harvard – Von Neumann; "10 000 ciclos garantizados de la Flash"; "100 000 ciclos garantizados de la EEPROM".

Columna derecha — **Memorias**: Flash – no volátil · SRAM – volátil · EEPROM – no volátil.

Centro — **Periféricos** (ATmega328P / **ESP32 DevKit V1**): lo más nuevo de la derecha abre la semana 2 (AVR → ESP32).

Tabla de conversión (dos cabeceras de pesos `128 64 32 16 8 4 2 1`):

| Columna | bits | hex | dec |
|---|---|---|---|
| ATmega328P | 1 0 0 0 0 0 0 1 | 0x81 | 129 |
| ESP32 | 0 1 1 0 0 1 0 0 | 0xC8 *(ver la nota)* | 100 |

> ⚠ **Error detectado en el apunte**: `0110 0100` = 4+64+... = 100 en decimal → `0x64` en hex, no `0xC8` (= 200). El valor binario y el decimal sí coinciden (100); la etiqueta hex estaba equivocada. Corregido aquí por trazabilidad.

## Foto 3 · DDRB / PORTB / PINB y manipulación de bits

> **DDRB ⇒** de peso (0 = entrada, 1 = salida) } Dirección *(margen: "Alta impedancia")*
> **PORTB ⇒** (al trabajar en salida) pone 0 o 1 lógicos
> **PINB ⇒** leer el voltaje real del pin
> *Usar para leer*

Ejercicios clásicos del apunte:

```text
// ¿Cuánto es 0x81 en binario?
0x81 ⇒ 1000 0001

// Escribe la línea que apaga el bit 3 (PORTB):
PORTB &= ~(1 << 3);
```

Enlaza con: Semana1_P2.md (los cuatro estados del pin; la máquina de estados del pull-up).

## Foto 4 · AVR vs ESP32 (beginner comparison)

> **AVR vs ESP32**
> En general, el ESP32 es considerablemente mejor que el ATmega328P
> UART – Serial
> GPIO matrix *(matriz de GPIO del ESP32)*

Pregunta que dejaba el apunte:

> *¿Cómo funcionan los dispositivos y periféricos?*

Enlaza con: Semana2_P1.md (GPIO matrix + IO_MUX, la central entre periféricos y pines).

## Foto 5 · Temporizadores: vocabulario y ejercicio

Transcripción del vocabulario:

- **Temporizador** – Periférico para contar el tiempo.
- **Contador** – Registro del temporizador (typeof: sumador que avanza en cada tick).
- **Reloj** – Señal que sube y baja a ritmo fijo, como un metrónomo.
- **APB** – Advanced Peripheral Bus.
- **Prescaler** – Divisor antes del contador (en ESP32, típicamente de 2 a ~65 535; nota marginal con tanteo "200 000" tachado: el máximo práctico del divisor de 16 bits es 65 535).
- **Resolución** – Duración de un tick (≈ periodo en el contexto del timer).

Fórmula y ejercicio del apunte:

```text
Tiempo = alarma × resolución        alarma = Tiempo ÷ resolución

Ejemplo: f = 10 000 ticks/s
resolución = 1/10 000 s = 0,0001 s = 100 µs
alarma = 25 000 ticks
```

(El tiempo implícito no escrito en el apunte: 25 000 × 100 µs = 2,5 s.)

- **Autorecarga** – Al alcanzar la alarma, el contador vuelve a 0.
- **ISR** – Rutina de servicio de interrupción (puente explícito hacia la semana 4).

Enlaza con: Semana3_P1.md / Semana3_P2.md.

## Vacíos observados

- No hay material manuscrito de la **Semana 4** (interrupciones externas) más allá de la sigla `ISR` en la foto 5.
- Los apuntes de timers están conceptualmente completos pero sin código (`timerBegin`, `timerAlarm`, etc.).
- Incertezas culturales del original: *(a)* la palabra inicial "Promoción" o similar en la foto 5 fue descartada por irrelevante al contenido; *(b)* el `hex: 0xC8` de la foto 2 es un error ya corregido arriba; *(c)* el prescaler marginal de 200 000 es un tanteo tachado, no un dato correcto.
