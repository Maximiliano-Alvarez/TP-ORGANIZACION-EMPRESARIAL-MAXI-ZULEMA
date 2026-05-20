# UNIVERSIDAD TECNOLOGICA NACIONAL  
Organización Empresarial - TP N°2

Alumnos: Rodriguez Zulema - Alvarez Maximiliano

**Escenario Seleccionado:** A - Análisis de Datos Climáticos  

---

## 1. Estructura Organizacional y Roles 
Para la ejecución operativa de este Sprint, el equipo se ha estructurado bajo metodologías ágiles, delimitando las responsabilidades funcionales para garantizar el control de procesos:

* **Rodriguez Zulema:** Lider, organizadora y QA del proyecto. Responsable de la planificación en Jira, definición del estándar de datos, revisión por pares (Peer Review) y aprobación de Pull Requests.
* **Alvarez Maximiliano:** Desarrollador Técnico. Responsable de la lógica algorítmica, adquisición del dataset crudo y programación de los scripts de limpieza y procesamiento analítico en Python.

---

##  2. Gobernanza de Datos y Descripción del Dataset
El clima se aborda como un *sistema abierto y complejo* que interactúa dinámicamente con su entorno a través de entradas (*inputs*) y salidas (*outputs*). 

Las corrientes de entrada de datos se registran en un dataset en formato CSV (`/data/datos_climaticos.csv`) proveniente de la base pública oficial de datos.gob.ar (registros de estación meteorológica aeroportuaria). El diccionario de datos se normaliza bajo el siguiente estándar técnico:

| Variable Técnica | Tipo de Datos | Descripción Operativa | Restricciones de Calidad (QA) / Estado |
| :--- | :--- | :--- | :--- |
| `Fecha` | Temporal (DD-MM-AA) | Clave primaria temporal del registro de mediciones. | Control de unicidad de registros. |
| `Temperatura_Max` | Numérico (Float) | Temperatura máxima absoluta diaria registrada (°C). | Contiene valores nulos (NaN) inducidos para validar el script. |
| `Temperatura_Min` | Numérico (Float) | Temperatura mínima absoluta diaria registrada (°C). | Control de consistencia (Debe ser menor o igual a Temperatura_Max). |
| `Precipitaciones_mm` | Numérico (Float) | Volumen de agua pluvial acumulada en 24 horas (mm). | **EXCLUIDA:** Variable sin registros en la fuente de origen. |

###  Nota de Control Interno y Auditoría (QA)
Luego de revisar el archivo de datos del aeropuerto, el área de **QA** constató una restricción técnica: la ausencia de registros íntegros para la variable `Precipitaciones_mm`. Para no generar errores se determinó una acción correctiva inmediata: **excluir dicha variable del procesamiento numérico y focalizar el modelo en las variables térmicas disponibles**. Grantizando la confiabilidad y la integridad estadística del software sin alterar la lógica sistémica del proyecto.

## 🛠️ 3. Guía de Ejecución y Despliegue Local
Para asegurar la compatibilidad del programa y el orden de los archivos en cualquier entorno de ejecución, siga estos pasos:

1. **Clonación del Repositorio:**
   ```bash
   git clone [https://github.com/MaximilianoAlvarez/tu-repositorio.git](https://github.com/MaximilianoAlvarez/tu-repositorio.git)

2. Entorno de Datos: Verificar la correcta disposición del archivo crudo en la ruta parametrizada: /data/datos_climaticos.csv.

3. Ejecución del Algoritmo: Iniciar el script principal de procesamiento estadístico mediante la consola:

    Bash
    python scripts/main.py

4. Mandato de Trazabilidad y Seguridad (Conventional Commits)
Este proyecto aplica una política estricta de trazabilidad integral entre la gestión de requerimientos (Jira) y el código fuente (GitHub). Ningún cambio o línea de código será integrado a la rama principal (main) sin la correspondiente validación de QA:

  - Estándar de Commits: Cada confirmación en Git deberá iniciar obligatoriamente con el ID único de la incidencia de Jira vinculada.

      - Formato exigido: <ID-JIRA>: <tipo>: <descripción>

      - Ejemplo Lider: CLIM-1.1: docs: inicialización del entorno Scrum en Jira y gobernanza base

        

Seguridad de la Información: Queda estrictamente prohibido cargar datos sensibles en el repositorio (rutas locales de la arquitectura del usuario, credenciales o tokens). Para asegurarnos utilizaremos el archivo .gitignore, de esta forma se filtra y deja afuera automaticamente cualquier archivo privado o temporal.
