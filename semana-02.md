# 📘 Semana 2 · Álgebra Booleana y Simplificación de Funciones Lógicas

> **🎯 Unidad:** 1 – Análisis de lógica combinacional con diseño clásico.  
> **💡 Resultado de aprendizaje:** Aplica leyes y teoremas booleanos para optimizar expresiones lógicas y circuitos digitales.

---

## 🚀 1. Introducción

El álgebra booleana es una herramienta matemática utilizada para representar y simplificar expresiones lógicas. Trabaja con dos valores posibles: **0** y **1**, que representan los estados de apagado y encendido dentro de los sistemas digitales.

> 📌 **¿Por qué es importante?** Su aplicación permite diseñar circuitos más sencillos, reducir la cantidad de compuertas y mejorar drásticamente el funcionamiento y costo de los sistemas digitales.

---

## 📐 2. Fundamentos del Álgebra Booleana

El álgebra booleana utiliza variables que solamente pueden tomar dos valores lógicos:

* 🔴 **`0`**: Falso, apagado o nivel lógico bajo.
* 🟢 **`1`**: Verdadero, encendido o nivel lógico alto.

Las operaciones fundamentales son:
* ✖️ **AND**: Multiplicación lógica.
* ➕ **OR**: Suma lógica.
* ⚠️ **NOT**: Negación lógica.

---

## ⚙️ 3. Operaciones Básicas

### ✖️ 3.1. Operación AND
La operación AND produce un valor de `1` únicamente cuando **todas** las variables tienen valor `1`.

* **Expresión:**
  $$Y = A \cdot B$$

---

### ➕ 3.2. Operación OR
La operación OR produce un valor de `1` cuando **al menos una** de las variables tiene valor `1`.

* **Expresión:**
  $$Y = A + B$$

---

### 🔄 3.3. Operación NOT
La operación NOT invierte el estado lógico de una variable (su complemento).

* **Expresión:**
  $$Y = A'$$

---

## 📜 4. Leyes del Álgebra Booleana

Las siguientes identidades y leyes son fundamentales para manipular y simplificar expresiones lógicas:

| 🏷️ Ley | ✖️ Forma Multiplicativa (AND) | ➕ Forma Aditiva (OR) |
| :--- | :--- | :--- |
| **Identidad** | $A \cdot 1 = A$ | $A + 0 = A$ |
| **Dominación** | $A \cdot 0 = 0$ | $A + 1 = 1$ |
| **Idempotencia** | $A \cdot A = A$ | $A + A = A$ |
| **Complemento** | $A \cdot A' = 0$ | $A + A' = 1$ |
| **Doble Negación** | $(A')' = A$ | — |
| **Conmutativa** | $A \cdot B = B \cdot A$ | $A + B = B + A$ |
| **Asociativa** | $(A \cdot B) \cdot C = A \cdot (B \cdot C)$ | $(A + B) + C = A + (B + C)$ |
| **Distributiva** | $A + (B \cdot C) = (A + B)(A + C)$ | $A \cdot (B + C) = A\cdot B + A\cdot C$ |
| **Absorción** | $A \cdot (A + B) = A$ | $A + A\cdot B = A$ |

---

## 🔗 5. Teoremas de De Morgan

Los teoremas de De Morgan permiten transformar expresiones booleanas complejas aplicando la negación de forma distribuida:

* **Primer Teorema (Negación del producto):**
  $$(A \cdot B)' = A' + B'$$

* **Segundo Teorema (Negación de la suma):**
  $$(A + B)' = A' \cdot B'$$

> 💡 **Utilidad:** Estos teoremas son indispensables para transformar compuertas y simplificar circuitos lógicos (por ejemplo, cambiar entre lógica NAND y NOR).

---

## ✂️ 6. Simplificación Algebraica

La simplificación consiste en reducir una expresión booleana utilizando las leyes y propiedades del álgebra de Boole.

### 📝 Ejemplo 1
* **Simplificar:** $F = A + A \cdot B$
* **Paso a paso:** Aplicando la ley de absorción.
* **Resultado:** 
  $$F = A$$

### 📝 Ejemplo 2
* **Simplificar:** $F = A \cdot B + A \cdot B'$
* **Paso a paso:** 
  1. Agrupando por factor común: $F = A(B + B')$
  2. Aplicando la ley del complemento ($B + B' = 1$): $F = A(1)$
* **Resultado:** 
  $$F = A$$

### 📝 Ejemplo 3
* **Simplificar:** $F = A \cdot B + A \cdot C$
* **Paso a paso:** Aplicando la propiedad distributiva inversa (factor común).
* **Resultado:** 
  $$F = A(B + C)$$

---

## 📦 7. Formas Canónicas

Las funciones booleanas pueden representarse de forma estándar mediante dos estructuras principales:

### ➕ 7.1. Suma de Productos (SOP - *Sum of Products*)
Es una expresión formada por la suma lógica de varios términos producto.
* **Ejemplo:** 
  $$F = A'B + AB'$$

### ✖️ 7.2. Producto de Sumas (POS - *Product of Sums*)
Es una expresión formada por el producto lógico de varios términos suma.
* **Ejemplo:** 
  $$F = (A + B)(A' + B')$$

---

## 🧩 8. Minitérminos y Maxitérminos

* **📦 Minitérminos:** Son productos lógicos que contienen **todas** las variables de la función (complementadas o sin complementar). Se utilizan para representar las combinaciones donde la función toma el valor **`1`**.
* **📦 Maxitérminos:** Son sumas lógicas que contienen **todas** las variables de la función. Se utilizan para representar las combinaciones donde la función toma el valor **`0`**.

---

## 🚨 9. Ejercicio de Aplicación

### 🎛️ Problema: Sistema de alarma con tres sensores
Se desea construir un sistema de alarma que se active cuando **al menos dos** de los tres sensores detecten una condición de peligro.

* **Variables de entrada:**
  * $A$: Sensor 1
  * $B$: Sensor 2
  * $C$: Sensor 3
* **Variable de salida:**
  * $F$: Activación de la alarma

#### 📊 Tabla de Verdad:
| 🌐 A | 🌐 B | 🌐 C | 🔔 F |
| :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | **0** |
| 0 | 0 | 1 | **0** |
| 0 | 1 | 0 | **0** |
| 0 | 1 | 1 | **1** |
| 1 | 0 | 0 | **0** |
| 1 | 0 | 1 | **1** |
| 1 | 1 | 0 | **1** |
| 1 | 1 | 1 | **1** |

* **Función lógica resultante (SOP):**
  $$F = A'BC + AB'C + ABC' + ABC$$
  *Simplificada:*
  $$F = AB + AC + BC$$

> 💡 Esta expresión activa la alarma de forma optimizada cuando al menos dos sensores se encuentran activos (`1`).



---

## 🏁 10. Conclusión

El álgebra booleana es el pilar matemático que permite modelar y optimizar el comportamiento de los sistemas digitales modernos. Mediante la aplicación metódica de sus leyes y teoremas, es posible condensar expresiones complejas en circuitos minimalistas, reduciendo el consumo energético, el costo de hardware y maximizando la velocidad de procesamiento.

---

## 📚 11. Bibliografía

* 📖 Mano, M. M. *Diseño digital*.
* 📖 Floyd, T. L. *Fundamentos de sistemas digitales*.
* 📖 Tocci, R. J., Widmer, N. S., y Moss, G. L. *Sistemas digitales: principios y aplicaciones*.
