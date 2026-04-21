<div align="center">
  
# 2026A-ISWD743-practica1
### Práctica Pentaho ETL
  
</div>

[![Andrea Chicaiza](https://img.shields.io/badge/Andrea_Chicaiza-andrea--m11-181717?style=for-the-badge&logo=github)](https://github.com/andrea-m11)<br><br>
[![Andreina](https://img.shields.io/badge/Andreina-Andreina--P-181717?style=for-the-badge&logo=github)](https://github.com/Andreina-P)<br><br>
[![Jose Arias](https://img.shields.io/badge/Jose_Arias-JoseDA0721-181717?style=for-the-badge&logo=github)](https://github.com/JoseDA0721)<br><br>
[![Juan Mateo Quisilema](https://img.shields.io/badge/Juan_Mateo-JuanMateoQ-181717?style=for-the-badge&logo=github)](https://github.com/JuanMateoQ)<br><br>
[![Juan Suarez](https://img.shields.io/badge/Juan_Suarez-juansuarezb-181717?style=for-the-badge&logo=github)](https://github.com/juansuarezb)<br><br>

>[!NOTE]
>
> Este repositorio contiene la implementación de diversos flujos de Extracción, Transformación y Carga (ETL) utilizando Pentaho Data Integration (PDI). El objetivo principal es demostrar la capacidad de procesar datos heterogéneos (Excel, CSV, JSON, XML y SQL) para convertirlos en información estructurada y lista para el análisis.

---

>[!NOTE]
>
> Objetivos específicos:
> * Comprender el proceso ETL (Extract, Transform, Load)
> * Trabajar con múltiples fuentes de datos (Interoperabilidad)
> * Aplicar transformaciones para limpieza y procesamiento
> * Generar salidas estructuradas
> * Escalabilidad: Implementación de entornos de base de datos mediante contenedores (Docker).

---

>[!IMPORTANT]
> Stack Tecnológico
> * Pentaho Data Integration (Spoon) 10.2.0.0-222.zip - ETL Tool: <br>
>   ![Pentaho](https://img.shields.io/badge/Pentaho-FF8C00?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTEyIDJMNyA3bDUgNSA1LTV6TTcgMTdsNSA1IDUtNXoiIGZpbGw9IndoaXRlIi8+PC9zdmc+&logoColor=white)
> * Java JDK 18.0.2.1 - Runtime <br>
> ![Java JDK](https://img.shields.io/badge/Java_JDK-18.0.2.1-007396?style=for-the-badge&logo=java&logoColor=white)
> * SQL Server Management Studio (SSMS) 22 - Management <br>
> ![SSMS](https://img.shields.io/badge/SSMS-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
> * Docker - DevOps <br>
> ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
> * Github  DevOps <br>
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

#### Paso 3: Carga (Output)
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
### 4. XML Input → Split Fields → Excel Output
---

>**Objetivo:**
- Utilizar un archivo XML como fuente de datos para aplicar la transformación **Split Fields**, permitiendo dividir un campo compuesto en dos campos independientes, y posteriormente exportar los datos procesados a un nuevo archivo Excel.
  
>**Dataset utilizado:**
- **Archivo de uso académico:** veterinaria.xml (disponible en la sección de recursos XML del repositorio de la práctica)
- **Campos:** ID, NOMBRE_MASCOTA, ESPECIE, RAZA, EDAD_AÑOS, PESO_KG, NOMBRE_PROPIETARIO, TELEFONO, FECHA_CONSULTA, DIAGNOSTICO, VETERINARIO.

>**Procedimiento:**
1. Se importaron datos desde un archivo XML, correspondientes a registros de consultas veterinarias.

    | ![alt text](Recursos-XML/XML-img1.png)|
    | :---: |
    | *Figura 1: Archivo XML de datos* |

    | ![alt text](Recursos-XML/XML-img2.png)|
    | :---: |
    | *Figura 2: Configuración de imput de datos XML* |

    | ![alt text](Recursos-XML/XML-img3.png)|
    | :---: |
    | *Figura 3: Preview de los datos XML* |

2. Se utilizó la transformación "Split Fields" para dividir el campo que contiene el nombre completo del propietario en dos campos separados de nombre y apellido. Se utilizó el espacio ' ' como delimitador para realizar la separación.

    | ![alt text](Recursos-XML/XML-img4.png)|
    | :---: |
    | *Figura 4: Configuración de la transformación de datos XML Split Fields de nombre y apellido de propietario* |


3. Después, se configuró el output para exportar los datos procesados a un nuevo archivo Excel.

    | ![alt text](Recursos-XML/XML-img5.png)|
    | :---: |
    | *Figura 5: Configuración de output a archivo Excel* |


4. Finalmente, se ejecutó la transformación para procesar los datos y generar el archivo Excel con la transformación aplicada.

    | ![alt text](Recursos-XML/XML-img6.png)|
    | :---: |
    | *Figura 6: Ejecución de la transformación* |


5. El resultado final es un archivo Excel con los datos procesados, donde se pueden observar claramente los campos separados de nombre y apellido del propietario.

    | ![alt text](Recursos-XML/XML-img7.png)|
    | :---: |
    | *Figura 7: Resultado de la transformación "Split Fields"* |

>**Comparación de datos antes y después de la transformación "Split Fields":**

| ![alt text](Recursos-XML/XML-img8.png) | ![alt text](Recursos-XML/XML-img9.png) |
| :---: | :---: |
| *Figura 8: Datos antes de la transformación* | *Figura 9: Datos después de la transformación* |

**Resultado:** Como se puede observar en la comparación, el campo "NOMBRE_PROPIETARIO" que contenía el nombre completo del propietario de la mascota (ej."Ana Torres") ha sido dividido correctamente en dos campos separados: "NOMBRE" y "APELLIDO" (ej. "Ana" y "Torres"), facilitando así el análisis y manejo de los datos.

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

Este flujo conecta el entorno dockerizado con Pentaho

Lectura: Extracción de registros de la tabla Ventas en SQL Server.
Transformación: Seleccionar elementos de la tabla (columnas)
Salida: Generación de un archivo XML/JSON con los resultados finales.


Primero, es necesario crear una conexión a una base de datos para poder obtener los registros del servidor empaquetado en el contenedor. Así, seleccionamos la opción de Database connections -> New y se nos presentará una ventana para seleccionar el tipo de motor de base de datos necesario. <br>

**Captura:**
![VentanaConfiguracionConexion](CapturasSQL/6.png) <br>

Primero, debemos de nombrar a la conexión "sql.containter" en este caso, ingresamos el host name (localhost), el nombre de la base de datos, puerto que se mapeo al momento de crear el contenedor, usuario (sa) y contraseña.

**Captura:**
![VentanaConfiguracionConexion2](CapturasSQL/7.png) <br>

A continuación, en el menú de "Options" pasamos a configurar algúnos parámetros necesarios para el correcto funcionamiento de la conexión"

Así, procedemos a crear una nueva transformación desde el menú superior.<br>
**Captura:**
![resultado](CapturasSQL/5.png) <br>

Después de ejecutar el comando para iniciar el proceso, observamos el correcto funcionamiento del flujo en los logs (Execution results) que presenta el sistema. Se observa que la transformación ha terminado correctamente y se procede a buscar el archivo en la ruta correspondiente.

**Captura:**
![resultado](CapturasSQL/resultado.png)

Finalmente, al encontrar el archivo resultante de la transformación, encontramos un archivo XML "salida" y al abrirlo se comprueba la correcta transformación de los datos creados en la base de datos para la tabla de ventas del contenedor hacia un archivo json con los registros.

**Captura:**
![resultado](CapturasSQL/transformacionXML.png) 


---

## Conclusiones

El uso de Pentaho facilita la automatización de procesos ETL, permitiendo integrar y transformar datos de diversas fuentes para su posterior análisis en sistemas de Business Intelligence.

---
