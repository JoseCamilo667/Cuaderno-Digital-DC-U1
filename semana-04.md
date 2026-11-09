# 📘 Semana 4 · Diseño de Circuitos Combinacionales Básicos

> **🎯 Unidad:** 1 – Análisis de lógica combinacional con diseño clásico.  
> **💡 Resultado de aprendizaje:** Diseña, analiza e implementa circuitos aritméticos combinacionales básicos (semisumadores y sumadores completos) aplicando metodologías clásicas de diseño.

---

## 🚀 1. Introducción

Los circuitos combinacionales son sistemas digitales cuyas salidas dependen **únicamente de los valores actuales de sus entradas** en un instante dado de tiempo.

> 📌 **Diferencia clave:** A diferencia de los circuitos secuenciales, **no almacenan información** (no tienen memoria) ni dependen de estados anteriores. Son esenciales para realizar operaciones aritméticas, decodificaciones y comparaciones en cualquier procesador.

---

## ⚙️ 2. Concepto de Circuitos Combinacionales

Un circuito combinacional es un arreglo interconectado de compuertas lógicas diseñado para aceptar un conjunto de entradas y producir salidas específicas.

### 🌟 Características principales:
* 🚫 **Ausencia de memoria:** No retienen información previa.
* ⚡ **Dependencia instantánea:** Las salidas cambian inmediatamente al modificarse las entradas (ignorando retardos de propagación).
* 📊 **Representación matemática:** Se describen formalmente mediante tablas de verdad y funciones booleanas.
* 🔌 **Implementación física:** Se construyen utilizando compuertas lógicas básicas y universales.

---

## 🛠️ 3. Procedimiento para el Diseño de Circuitos Combinacionales

Para diseñar un sistema combinacional desde cero de forma estructurada, se sigue esta metodología de 8 pasos:

1. 🔍 **Analizar el problema:** Comprender detalladamente qué se desea lograr.
2. 🏷️ **Identificar entradas y salidas:** Definir claramente qué variables controlan el sistema y cuáles son los resultados esperados.
3. 🔤 **Asignar variables lógicas:** Asignar letras o símbolos a cada señal.
4. 📊 **Elaborar la tabla de verdad:** Relacionar todas las combinaciones posibles de entrada con sus respectivas salidas.
5. ✍️ **Obtener funciones booleanas:** Extraer las expresiones algebraicas (por SOP o POS).
6. ✂️ **Simplificar expresiones:** Utilizar álgebra booleana o Mapas de Karnaugh para optimizar el circuito.
7. ⚡ **Dibujar el circuito lógico:** Esquematizar el diagrama esquemático con compuertas.
8. 🧪 **Comprobar funcionamiento:** Validar mediante simulación lógica o pruebas de hardware.

---

## ➕ 4. Semisumador (*Half Adder*)

El semisumador es un circuito aritmético combinacional básico que permite sumar **dos bits de un solo dígito** ($A$ y $B$).

### 📌 Entradas y Salidas:
* **Entradas:**
  * $A$: Primer bit sumando.
  * $B$: Segundo bit sumando.
* **Salidas:**
  * $S$: Resultado de la suma (bit menos significativo).
  * $C$: Acarreo (*Carry* de salida).

---

### 📊 4.1. Tabla de Verdad
| 🌐 A | 🌐 B | ➕ S (Suma) | 📦 C (Acarreo) |
| :---: | :---: | :---: | :---: |
| 0 | 0 | **0** | **0** |
| 0 | 1 | **1** | **0** |
| 1 | 0 | **1** | **0** |
| 1 | 1 | **0** | **1** |

---

### 📐 4.2. Funciones Booleanas del Semisumador
* **Suma ($S$ - Compuerta XOR):**
  $$S = A \oplus B$$
* **Acarreo ($C$ - Compuerta AND):**
  $$C = A \cdot B$$

---

## ➕ 5. Sumador Completo (*Full Adder*)

El sumador completo es un circuito más avanzado que permite sumar **tres bits simultáneamente**: dos bits de entrada principales ($A$ y $B$) más el acarreo de entrada proveniente de una etapa inferior ($C_{in}$).

### 📌 Entradas y Salidas:
* **Entradas:**
  * $A$: Primer bit.
  * $B$: Segundo bit.
  * $C_{in}$: Acarreo de entrada (*Carry Input*).
* **Salidas:**
  * $S$: Resultado de la suma.
  * $C_{out}$: Acarreo de salida (*Carry Output*).

---

### 📊 5.1. Tabla de Verdad
| 🌐 A | 🌐 B | 🌐 $C_{in}$ | ➕ S (Suma) | 📦 $C_{out}$ (Acarreo) |
| :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | **0** | **0** |
| 0 | 0 | 1 | **1** | **0** |
| 0 | 1 | 0 | **1** | **0** |
| 0 | 1 | 1 | **0** | **1** |
| 1 | 0 | 0 | **1** | **0** |
| 1 | 0 | 1 | **0** | **1** |
| 1 | 1 | 0 | **0** | **1** |
| 1 | 1 | 1 | **1** | **1** |

---

### 📐 5.2. Funciones Booleanas del Sumador Completo
* **Suma ($S$):**
  $$S = A \oplus B \oplus C_{in}$$
* **Acarreo de Salida ($C_{out}$):**
  $$C_{out} = A \cdot B + A \cdot C_{in} + B \cdot C_{in}$$

---

## 🔗 6. Sumador Paralelo de Cuatro Bits

Un sumador paralelo de cuatro bits permite sumar dos números binarios completos de 4 bits cada uno (por ejemplo, $A_3 A_2 A_1 A_0$ y $B_3 B_2 B_1 B_0$).

> ⚙️ **Arquitectura:** Está compuesto por la conexión en cascada de **cuatro sumadores completos**. Cada etapa procesa un bit de peso correspondiente y propaga el acarreo (*carry ripple*) hacia la siguiente etapa superior.

* **Ejemplo numérico de operación binaria:**

```text
       0 1 0 1  (5 en decimal)
     + 0 0 1 1  (3 en decimal)
     ---------
       1 0 0 0  (8 en decimal)
