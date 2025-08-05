# Guía Rápida: Números Complejos en HP Prime (Modo CAS)

**Página 1 de 2: Fundamentos y Operaciones Básicas**

---

#### **1. Configuración Inicial (¡Hacer esto primero!)**

Una configuración correcta es esencial. De lo contrario, los resultados no coincidirán con los de tus apuntes.

1.  Presiona `Shift` + `CAS` para ir a la **Configuración del CAS**.
2.  Asegúrate de que estos tres ajustes estén así:
    *   **Medida angular (Angle Measure):** `Radianes`.
    *   **Formato Complejo (Complex):** `a+b*i`.
    *   **Sistema de Coordenadas (Coord. System):** `Cartesiano`.

#### **2. Introduciendo Números Complejos**

*   **Unidad Imaginaria `i`:** Para escribir `i`, presiona **`Shift` + `2`**.
*   **Ejemplo de entrada:** Para escribir $z = 3 + 4i$, teclea: `3 + 4 * SHIFT 2`

#### **3. Funciones Fundamentales**

Estas son las operaciones más comunes. Puedes escribirlas directamente o encontrarlas en `Toolbox` → `CAS` → `Matem.` → `Compleja`.

| Concepto | Notación | Comando HP Prime | Ejemplo (usando z = 3+4i) |
| :--- | :--- | :--- | :--- |
| **Parte Real** | $\text{Re}(z)$ | `RE(z)` | `RE(3+4*i)` → `3` |
| **Parte Imaginaria**| $\text{Im}(z)$ | `IM(z)` | `IM(3+4*i)` → `4` |
| **Módulo** | $|z|$ | `ABS(z)` | `ABS(3+4*i)` → `5` |
| **Argumento** | $\text{arg}(z)$ | `ARG(z)` | `ARG(3+4*i)` → `0.927...` |
| **Conjugado** | $\bar{z}$ | `CONJ(z)` | `CONJ(3+4*i)` → `3-4*i` |

<br>
<br>

---

**Página 2 de 2: Forma Polar, Potencias y Raíces**

---

#### **4. Conversiones: Binómica ↔ Polar**

La forma polar $z = r(\cos\theta + i\sin\theta)$ es clave para potencias y raíces.

*   **De Binómica a Polar:** Usa `polar_coordinates(z)`.
    *   **Entrada:** `polar_coordinates(3+4*i)`
    *   **Salida:** `[5, 0.9272]` (Esto es `[r, θ]`)

*   **De Polar a Binómica:** El método más directo es usar el símbolo de ángulo `∠`.
    *   **Sintaxis:** `r∠θ` (Para `∠`, presiona `Shift` + `x`)
    *   **Entrada:** `5∠0.927295218`
    *   **Salida:** `3+4*i`
    *   **Nota (Fórmula de Euler):** Este método es un atajo para la definición matemática `r * e^(i*θ)`. Puedes introducir `5 * e^(i * 0.927295218)` y obtendrás el mismo resultado. Es útil para familiarizarte con la fórmula.

#### **5. Potencias y Raíces (Teorema de De Moivre)**

*   **Potencias ($z^n$):** Se calculan directamente.
    *   **Ejemplo:** Para calcular $(1+i)^5$, introduce: `(1+i)^5`
    *   **Resultado:** `-4+4*i`

*   **Raíces n-ésimas ($\sqrt[n]{z}$):**
    *   `z^(1/n)` o `sqrt(z)` solo te dará la **raíz principal**.
    *   **Para obtener TODAS las n raíces**, puedes usar dos métodos:

    *   **Método 1: Generador de Listas (Recomendado)**
        *   **Sintaxis:** `[fórmula(k) for k from 0 to n-1]`
        *   **Ejemplo (3 raíces cúbicas de 8):**
            *   **Entrada:** `[8^(1/3)*e^(2*π*i*k/3) for k from 0 to 2]`
            *   **Salida:** `{2, -1+1.732...*i, -1-1.732...*i}`

    *   **Método 2: Comando `makelist`**
        *   Este comando hace lo mismo que el anterior, pero puede ser más fácil si lo buscas en el catálogo de herramientas (`Toolbox` > `CAS` > `Lista`).
        *   **Sintaxis:** `makelist(fórmula(k), k, 0, n-1)`
        *   **Ejemplo (3 raíces cúbicas de 8):**
            *   **Entrada:** `makelist(8^(1/3)*e^((2*π*i*k)/3), k, 0, 2)`
            *   **Salida:** `{2, -1+1.732...*i, -1-1.732...*i}`

#### **6. Consejos y Atajos**

*   **Acceso Rápido a Comandos:** Presiona la tecla `Toolbox` (a veces etiquetada como `Ctlg` o similar), ve a la pestaña `CAS` y navega a `Matem.` → `Compleja` para ver una lista de todas las funciones.
*   **¡Revisa el Modo Angular!** Si tus resultados con `ARG` o la forma polar no tienen sentido, lo más probable es que la calculadora esté en Grados (`Degrees`) en lugar de Radianes.
*   **Usa el Entorno CAS:** Para álgebra simbólica y resolución de ecuaciones, asegúrate de estar en la vista `CAS` (presionando la tecla `CAS`).
