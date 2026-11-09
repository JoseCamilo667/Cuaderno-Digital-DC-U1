# Semana 1 · Sistemas numéricos, códigos y compuertas lógicas

**Unidad:** 1 – Análisis de lógica combinacional con diseño clásico.

**Resultado de aprendizaje:** Diseña e implementa circuitos combinacionales
básicos utilizando técnicas de diseño clásico.

---

## 1. Introducción

Los sistemas digitales utilizan señales que representan dos estados
lógicos: 0 y 1. Estos valores permiten representar información,
realizar operaciones matemáticas y construir circuitos electrónicos.

En esta semana se estudian los sistemas numéricos binario, octal,
decimal y hexadecimal, además de la aritmética binaria, los códigos
digitales y las principales compuertas lógicas.

Estos conocimientos son necesarios para comprender cómo funciona
internamente una computadora y cómo se representa la información
mediante circuitos electrónicos.

## 2. Sistemas numéricos

Un sistema numérico es un conjunto de símbolos y reglas que permite
representar cantidades.

En electrónica digital se utilizan principalmente cuatro sistemas:

| Sistema | Base | Dígitos utilizados |
|---------|------|--------------------|
| Binario | 2 | 0 y 1 |
| Octal | 8 | 0 al 7 |
| Decimal | 10 | 0 al 9 |
| Hexadecimal | 16 | 0 al 9 y A al F |

### 2.1 Sistema decimal

Es el sistema que utilizamos normalmente en nuestra vida cotidiana.
Su base es 10 y utiliza diez dígitos.

Ejemplo:

253 = 2 × 100 + 5 × 10 + 3 × 1

253 = 200 + 50 + 3

### 2.2 Sistema binario

Es el sistema utilizado por las computadoras y los circuitos digitales.
Su base es 2 y solamente utiliza los números 0 y 1.

Cada dígito binario recibe el nombre de bit.

Ejemplo:

1011₂

= 1 × 8 + 0 × 4 + 1 × 2 + 1 × 1

= 8 + 0 + 2 + 1

= 11₁₀

### 2.3 Conversión de decimal a binario

Para convertir un número decimal a binario se divide sucesivamente
entre 2 y se anotan los residuos. Finalmente, se leen los residuos
desde abajo hacia arriba.

Ejemplo: Convertir 25 a binario.

25 ÷ 2 = 12, residuo 1
12 ÷ 2 = 6, residuo 0
6 ÷ 2 = 3, residuo 0
3 ÷ 2 = 1, residuo 1
1 ÷ 2 = 0, residuo 1

Resultado:

25₁₀ = 11001₂

### 2.4 Sistema octal

Su base es 8 y utiliza los dígitos del 0 al 7.

Para convertir un número binario a octal se agrupan los bits
de tres en tres, comenzando desde la derecha.

Ejemplo:

10011101₂

Agrupación:

010 011 101

Conversión:

010 = 2
011 = 3
101 = 5

Resultado:

10011101₂ = 235₈

### 2.5 Sistema hexadecimal

Su base es 16. Utiliza los números del 0 al 9 y las letras
A, B, C, D, E y F.

| Decimal | Hexadecimal |
|---------|-------------|
| 10 | A |
| 11 | B |
| 12 | C |
| 13 | D |
| 14 | E |
| 15 | F |

Para convertir de binario a hexadecimal se agrupan los bits
de cuatro en cuatro.

Ejemplo:

10011101₂

1001 = 9
1101 = D

Resultado:

10011101₂ = 9D₁₆

## 3. Aritmética binaria

La aritmética binaria permite realizar operaciones matemáticas
utilizando únicamente los valores 0 y 1.

### 3.1 Suma binaria

Las reglas principales son:

| Operación | Resultado |
|-----------|-----------|
| 0 + 0 | 0 |
| 0 + 1 | 1 |
| 1 + 0 | 1 |
| 1 + 1 | 10 |
| 1 + 1 + 1 | 11 |

Cuando se obtiene un resultado de dos bits, el bit de la izquierda
se lleva a la siguiente columna. Esto se conoce como acarreo.

Ejemplo:

```text
   1011
 + 0110
 -------
  10001
