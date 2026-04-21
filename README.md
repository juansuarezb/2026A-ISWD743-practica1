# 2026A-ISWD743-practica1
# Práctica Pentaho ETL
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-FF6C37?style=for-the-badge&logo=power-bi&logoColor=white)
![EPN](https://img.shields.io/badge/Escuela_Politécnica_Nacional-003366?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTEyIDJMMiA3bDEwIDUgMTAtNS0xMC01ek0yIDE3bDEwIDUgMTAtNU0yIDEybDEwIDUgMTAtNSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyIi8+PC9zdmc+&logoColor=white)
![Facultad de Ingeniería en Sistemas](https://img.shields.io/badge/FIS-Facultad_Ingeniería_Sistemas-003366?style=for-the-badge)

# Integrantes
[![Andrea Chicaiza](https://img.shields.io/badge/Andrea_Chicaiza-andrea--m11-181717?style=for-the-badge&logo=github)](https://github.com/andrea-m11)<br><br>
[![Andreina](https://img.shields.io/badge/Andreina-Andreina--P-181717?style=for-the-badge&logo=github)](https://github.com/Andreina-P)<br><br>
[![Jose Arias](https://img.shields.io/badge/Jose_Arias-JoseDA0721-181717?style=for-the-badge&logo=github)](https://github.com/JoseDA0721)<br><br>
[![Juan Mateo Quisilema](https://img.shields.io/badge/Juan_Mateo-JuanMateoQ-181717?style=for-the-badge&logo=github)](https://github.com/JuanMateoQ)<br><br>
[![Juan Suarez](https://img.shields.io/badge/Juan_Suarez-juansuarezb-181717?style=for-the-badge&logo=github)](https://github.com/juansuarezb)<br><br>

>[!NOTE]
>
> Descripción: <br>
> * Implementación de procesos ETL utilizando Pentaho Data Integration (PDI - Spoon), trabajando con diferentes tipos de entrada (Input) y transformaciones para el procesamiento de datos.

---

>[!NOTE]
>
> Objetivos:
> * Comprender el proceso ETL (Extract, Transform, Load)
> * Trabajar con múltiples fuentes de datos
> * Aplicar transformaciones para limpieza y procesamiento
> * Generar salidas estructuradas

---

>[!IMPORTANT]
> Tecnologías utilizadas:
> * Pentaho Data Integration (Spoon)
>   ![Pentaho](https://img.shields.io/badge/Pentaho-FF8C00?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTEyIDJMNyA3bDUgNSA1LTV6TTcgMTdsNSA1IDUtNXoiIGZpbGw9IndoaXRlIi8+PC9zdmc+&logoColor=white)
> * Java JDK
> ![Java JDK](https://img.shields.io/badge/Java_JDK-18.0.0-007396?style=for-the-badge&logo=java&logoColor=white)
> * SQL Server Managamente Studio 22
> ![SSMS](https://img.shields.io/badge/SSMS-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
> * Docker
> ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
> * Github
> ![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
> * Archivos: Excel, CSV, JSON, XML, Tablas de Bases de datos SQL
> ![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
> ![JSON](https://img.shields.io/badge/json-5E5C5C?style=for-the-badge&logo=json&logoColor=white)
> ![SQL Server](https://img.shields.io/badge/Microsoft_SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)


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
Por último, se procederá a crear un entorno dockerizado para desplegar un contenedor para el SGBD (Sistema Gestor de Base de Datos) SQL Server 2025. Para ello es necesario tener instalado Docker Desktop para una mejor gestión de los contenedores. Así, se muestra a continuación la interfaz esperada al iniciar el software: 

**Captura:**
![DockerDesktop](CapturasSQL/1.png)

A continuación, es necesario crear un contenedor a partir de la imagen de SQL Server disponible en Docker Hub. Es necesario configurar algunas variables de entorno para el correcto funcionamiento del contenedor. 

## Levantar SQL Server con Docker

```bash
docker run -d \
  --name sqlserver2025 \
  --hostname sqlserver2025 \
  -e ACCEPT_EULA=Y \
  -e MSSQL_SA_PASSWORD=MiPassword123! \
  -e MSSQL_PID=Developer \
  -p 1433:1433 \
  -v sqlserver2025_data:/var/opt/mssql \
  mcr.microsoft.com/mssql/server:2025-latest
```

Así, tendremos levantado el contenedor de SQL Server como se muestra a continuación:

**Captura:**
![sqlserver-container](CapturasSQL/2.png)
---

## Resultados

* Integración de múltiples fuentes de datos
* Transformación y limpieza de información
* Generación de archivos procesados correctamente

---

## Conclusiones

El uso de Pentaho facilita la automatización de procesos ETL, permitiendo integrar y transformar datos de diversas fuentes para su posterior análisis en sistemas de Business Intelligence.

---
