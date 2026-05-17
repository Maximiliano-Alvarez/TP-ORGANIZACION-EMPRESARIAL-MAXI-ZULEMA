# TP-ORGANIZACION-EMPRESARIAL-MAXI-ZULEMA
Trabajo Práctico UTN - Organización Empresarial
# 🌦️ Trabajo Práctico N° 2: Gestión Colaborativa y Control de Versiones
**Materia:** Organización Empresarial - UTN FRBA  
**Célula de Desarrollo:** CLIM (Análisis de Sistemas Dinámicos Complejos)  
**Escenario Seleccionado:** Escenario A - Análisis de Datos Climáticos  

---

## 👥 1. Estructura Organizacional y Roles (Unidad 4)
Para la ejecución operativa de este Sprint, el equipo se ha estructurado bajo metodologías ágiles, delimitando las responsabilidades funcionales para garantizar el control de procesos:

* **Zulema Rodriguez (P1 / P3):** Administradora del Proyecto, Aseguramiento de la Calidad (QA) y Gobernanza de la Información. Responsable de la planificación en Jira, definición del estándar de datos, revisión por pares (Peer Review) y aprobación de Pull Requests.
* **Maximiliano Alvarez (P2):** Desarrollador Técnico / Ingeniero de Software. Responsable de la lógica algorítmica, adquisición del dataset crudo y programación de los scripts de limpieza y procesamiento analítico en Python.

---

## 📊 2. Gobernanza de Datos y Descripción del Dataset
En concordancia con la **Teoría General de Sistemas (Unidad 1)**, el clima se aborda como un *sistema abierto y complejo* que intercambia materia y energía con su entorno. Las entradas (*inputs*) del sistema se registran en un dataset en formato CSV (`/data/datos_climaticos.csv`) estructurado bajo el siguiente diccionario de datos normalizado:

| Variable Técnica | Tipo de Datos | Descripción Operativa | Restricciones de Calidad (QA) |
| :--- | :--- | :--- | :--- |
| `Fecha` | Temporal (YYYY-MM-DD) | Clave primaria temporal del registro de mediciones. | Formato ISO estricto. Sin duplicados. |
| `Temperatura_Max` | Numérico (Float) | Temperatura máxima absoluta registrada en el día (°C). | Contiene valores nulos simulados para validar script. |
| `Humedad_Porcentaje` | Numérico (Integer) | Porcentaje de humedad relativa promedio en la atmósfera. | Rango válido obligatorio: 0% a 100%. |
| `Precipitaciones_mm` | Numérico (Float) | Volumen de agua de lluvia acumulada en 24 horas (mm). | Valores mayores o iguales a cero. |

---

## 🛠️ 3. Guía de Ejecución y Despliegue Local
Para garantizar la reproducibilidad del sistema y el control de dependencias, siga estos pasos:

1. **Clonación del Repositorio:**
   ```bash
   git clone [https://github.com/MaximilianoAlvarez/tu-repositorio.git](https://github.com/MaximilianoAlvarez/tu-repositorio.git)
