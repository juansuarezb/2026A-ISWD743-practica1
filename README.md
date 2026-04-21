# 2026A-ISWD743-practica1
# Práctica Pentaho ETL

# 🧠 Práctica: Pentaho Data Integration (ETL)

## Descripción

Implementación de procesos ETL utilizando Pentaho Data Integration (PDI - Spoon), trabajando con diferentes tipos de entrada (Input) y transformaciones para el procesamiento de datos.

---

## Objetivos

* Comprender el proceso ETL (Extract, Transform, Load)
* Trabajar con múltiples fuentes de datos
* Aplicar transformaciones para limpieza y procesamiento
* Generar salidas estructuradas

---

## Tecnologías utilizadas

* Pentaho Data Integration (Spoon)
* Java JDK
* Archivos: Excel, CSV, JSON, XML
* (Opcional) Base de datos

---

## Transformaciones realizadas

### 1. Excel Input → Replace in String → Excel Output

**Descripción:**
Se cargaron datos desde un archivo Excel, se realizó limpieza de texto y se exportó el resultado.

**Captura:**
![excel](capturas/excel.png)

---

### 2. CSV Input → String Operation (Upper) → Text Output

#### Dataset Utilizado
* **Archivo:** `babyNamesUSYOB-full.csv`
* **Campos:** `YearOfBirth`, `Name`, `Sex`, `Number`.

**Descripción:**
#### Paso 1: Extracción (Input)
Se configuró un paso de **CSV file input** para leer el archivo original. Se definió el delimitador por coma (`,`) y se obtuvieron los campos con sus respectivos tipos de datos (Integer para el año y cantidad, String para el nombre y sexo).

#### Paso 2: Transformación (String Operations)
Para normalizar la información, se utilizó el paso **String operations**. Se seleccionó la columna `Name` y se aplicó la transformación **Upper** para convertir todos los nombres de minúsculas a **MAYÚSCULAS**.

### Paso 3: Carga (Output)
Los datos transformados se enviaron a un archivo de salida llamado `Salida.csv` mediante el paso **Text file output**. En la configuración de salida:
* Se cambió el separador a punto y coma (`;`).
* Se forzó la inclusión de los nuevos campos transformados en la pestaña *Fields*.

#### Evidencias del Proceso

##### Diseño de la Transformación en Spoon
Aquí se muestra el flujo completo desde la lectura hasta la escritura:
![Diseño ETL](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20083251.png)

##### Configuración de Input
![Configuración Input](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20082102.png)

##### Configuración de la Transformación de Texto
![Configuración String Ops](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20082836.png)

##### Configuración Output
![Configuración Output](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20083246.png)

##### Vista Previa de los Datos (Preview)
![Preview Datos](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20084443.png)

##### Vista posterior a la transformación

![Final Datos](./Capturas%20csv/Captura%20de%20pantalla%202026-04-21%20084433.png)

#### Resultados
* **Archivo Original:** Los nombres presentaban un formato de tipo título (ej. "Mary").
* **Archivo de Salida:** Los nombres se encuentran totalmente en mayúsculas (ej. "MARY"), listos para ser procesados en un Data Warehouse.

---

### 3. JSON Input → Select Values → Output

**Descripción:**
Se procesaron datos en formato JSON, seleccionando campos relevantes para análisis.

**Captura:**
![json](capturas/json.png)

---

### 4. XML Input → Sort Rows → Output

**Descripción:**
Se cargaron datos XML y se ordenaron según un criterio definido.

**Captura:**
![xml](capturas/xml.png)

---

### 5. Table Input → Calculator → Output

**Descripción:**
Se extrajeron datos desde una base de datos y se realizaron cálculos sobre los mismos.

**Captura:**
![db](capturas/db.png)

---

## Resultados

* Integración de múltiples fuentes de datos
* Transformación y limpieza de información
* Generación de archivos procesados correctamente

---

## Conclusiones

El uso de Pentaho facilita la automatización de procesos ETL, permitiendo integrar y transformar datos de diversas fuentes para su posterior análisis en sistemas de Business Intelligence.

---

## Autores

Juan Diego Suarez

