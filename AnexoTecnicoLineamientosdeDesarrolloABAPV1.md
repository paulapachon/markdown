






**Tabla de Contenido**

- [Objetivo](#objetivo)
- [1. Nomenclaturas ordenes de transporte](#1-nomenclaturas-ordenes-de-transporte)
  - [1.1 Nomenclatura OT's](#11-nomenclatura-ots)
- [2. Convenciones](#2-convenciones)
- [3. Declaración de Objetos Globales](#3-declaración-de-objetos-globales)
  - [3.1 Creación de Paquete](#31-creación-de-paquete)
  - [3.2 Programa](#32-programa)
  - [3.3 Transacción](#33-transacción)
  - [3.4 Creación de Include](#34-creación-de-include)
  - [3.5 Creación de Grupo de Funciones](#35-creación-de-grupo-de-funciones)
  - [3.6 Creación de Módulos de Función](#36-creación-de-módulos-de-función)
  - [3.7 Creación Tabla](#37-creación-tabla)
  - [3.8 Creación Vista](#38-creación-vista)
  - [3.9 Creación Estructura](#39-creación-estructura)
    - [3.9.1 Estructura Append](#391-estructura-append)
  - [3.10 Creación Tipo Tabla](#310-creación-tipo-tabla)
  - [3.11 Creación Elemento De Datos](#311-creación-elemento-de-datos)
  - [3.12 Creación de Dominio](#312-creación-de-dominio)
    - [3.12.1 Los dominios con ámbito de valores](#3121-los-dominios-con-ámbito-de-valores)
  - [3.13 Creación Ayuda de Búsqueda](#313-creación-ayuda-de-búsqueda)
  - [3.14 Clase De Mensaje](#314-clase-de-mensaje)
- [4. Modificaciones](#4-modificaciones)
  - [4.1 Encabezado](#41-encabezado)
  - [4.2 Comentario Línea](#42-comentario-línea)
- [5. Declaración de datos globales](#5-declaración-de-datos-globales)
  - [5.1 Declaración de Tablas](#51-declaración-de-tablas)
  - [5.2 Declaración variable](#52-declaración-variable)
    - [5.2.1 Types](#521-types)
    - [5.2.2 Tablas Internas](#522-tablas-internas)
    - [5.2.3 Declaración Work Area](#523-declaración-work-area)
    - [5.2.4 Declaración Field-symbols](#524-declaración-field-symbols)
    - [5.2.5 Declaración Constantes](#525-declaración-constantes)
    - [5.2.6 Rangos](#526-rangos)


- [Objetivo](#objetivo)
- [1. Nomenclaturas ordenes de transporte](#1-nomenclaturas-ordenes-de-transporte)
  - [1.1 Nomenclatura OT's](#11-nomenclatura-ots)
- [2. Convenciones](#2-convenciones)
- [3. Declaración de Objetos Globales](#3-declaración-de-objetos-globales)
  - [3.1 Creación de Paquete](#31-creación-de-paquete)
  - [3.2 Programa](#32-programa)
  - [3.3 Transacción](#33-transacción)
  - [3.4 Creación de Include](#34-creación-de-include)
  - [3.5 Creación de Grupo de Funciones](#35-creación-de-grupo-de-funciones)
  - [3.6 Creación de Módulos de Función](#36-creación-de-módulos-de-función)
  - [3.7 Creación Tabla](#37-creación-tabla)
  - [3.8 Creación Vista](#38-creación-vista)
  - [3.9 Creación Estructura](#39-creación-estructura)
    - [3.9.1 Estructura Append](#391-estructura-append)
  - [3.10 Creación Tipo Tabla](#310-creación-tipo-tabla)
  - [3.11 Creación Elemento De Datos](#311-creación-elemento-de-datos)
  - [3.12 Creación de Dominio](#312-creación-de-dominio)
    - [3.12.1 Los dominios con ámbito de valores](#3121-los-dominios-con-ámbito-de-valores)
  - [3.13 Creación Ayuda de Búsqueda](#313-creación-ayuda-de-búsqueda)
  - [3.14 Clase De Mensaje](#314-clase-de-mensaje)
- [4. Modificaciones](#4-modificaciones)
  - [4.1 Encabezado](#41-encabezado)
  - [4.2 Comentario Línea](#42-comentario-línea)
- [5. Declaración de datos globales](#5-declaración-de-datos-globales)
  - [5.1 Declaración de Tablas](#51-declaración-de-tablas)
  - [5.2 Declaración variable](#52-declaración-variable)
    - [5.2.1 Types](#521-types)
    - [5.2.2 Tablas Internas](#522-tablas-internas)
    - [5.2.3 Declaración Work Area](#523-declaración-work-area)
    - [5.2.4 Declaración Field-symbols](#524-declaración-field-symbols)
    - [5.2.5 Declaración Constantes](#525-declaración-constantes)
    - [5.2.6 Rangos](#526-rangos)

# Objetivo

El presente anexo se crea para contar con un marco referencial que permita unificar la nomenclatura y 
buenas prácticas a utilizar en los desarrollos ABAP, contando con pautas y recomendaciones para 
programar.

# 1. Nomenclaturas ordenes de transporte
## 1.1 Nomenclatura OT's

 **\<Tipo>-\<MO> \<NNN> \<BBB> \<DDD> \<Versión>** 

- **Tipo** - CU (Customizing), WB (Workbench)
- **MO**- Módulo
- **NNN**- Iniciales del Nombre del desarrollador
- **BBB**: Número del Caso
- **DDD**: Descripción caso
- **Versión**: Consecutivo si existen versiones con la versión empezando en 001

**Recomendaciones:**

- Cuando se vaya modificar un objeto existente se debe verificar que la versión activa esté 
igual en los otros ambientes calidad y productivo.

- En caso de no ser consistente se debe notificar al líder funcional y líder técnico para 
determinar qué acción tomar.

- Se debe garantizar que al momento de realizar la liberación de la orden los objetos se 
encuentren bloqueados y la versión activa pertenezca a la orden a liberar. 

- Para el transporte de las ordenes a calidad, se debe realizar Ordenes transporte de copia, 
para este caso se debe adicionar a la descripción de la orden el sufijo CC + Consecutivo 
(Para este consecutivo se incrementa cada vez que se realice un transporte a calidad).

- El transporte de las órdenes a calidad los realizará el Job de la cola de transportes.

- La orden principal solo se debe liberar cuando el funcional de el VoBo para paso a 
producción

# 2. Convenciones

| CONVENCIONES | MO = Modulo          |
|--------------|----------------------|
|              |  DM = Datos Maestros |
|              |  BW                  |
|              |  FI                  |
|              |  ISH_MED             |
|              | ISH_PA               |
|              |  ISH_PM              |
|              | MM                   |
|              | QM = Calidad         |
|              | PM = Mantenimiento   |
|              | SD                   |


# 3. Declaración de Objetos Globales
## 3.1 Creación de Paquete

Para la creación de paquetes se manejará de la siguiente manera **ZPKGAAA**.

- **Z**  Por definición SAP 
- **PKG** Constante que identifica el paquete
- **AAA** Módulo de Aplicación o proyecto, son las iniciales o identificador del 
mismo, no debe superar los 3 caracteres

## 3.2 Programa

Los nombres de estos objetos tendrán la siguiente forma **ZMMTP_NNNN**.

- **Z**   Por definición SAP 
- **TP**  Tipo de programa
- **MM**  Módulo SAP o proyecto
- **NNNN** Descripción literal de la funcionalidad (Separado por _)
- **VNN**  Versión de la Función (Esta nomenclatura es opcional)


## 3.3 Transacción

Los nombres de estos objetos tendrán la siguiente forma **ZMMNNN**.

- **Z**   Por definición SAP
- **MM**  Módulo SAP o proyecto 
- **NNN** Número consecutivo

## 3.4 Creación de Include 

Para los programas **INCLUDE** (tipo “I” en sus atributos), se utilizarán para los siguientes 
casos:

- Para estructurar programas con muchas líneas de código. 
-  Para generar código re-utilizable en otros programas.
  
Los nombres de estos objetos tendrán la siguiente forma **Z[MM][TP][NNNN]_XXX**

| Include       | Descripción                                                                                                                                                                                             |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ZMMTPNNNN_TOP | Todas las declaraciones iniciales. <br/>Ejm: tablas, estructuras, variables, Type-Pools, table Controls, etc.<br/>Adicionalmente se puede utilizar para la definición de los métodos <br/>de una clase. |
| ZMMTPNNNN_EVE | Los parámetros de selección. <br/>El proceso principal.<br/>Eventos, Ejm: INITIALIZATION. START-OFSELECTION, AT SELECTION <br/>SCREEN, etc                                                              |
| ZMMTPNNNN_F01 | Las subrutinas del programa.                                                                                                                                                                            |
| ZMMTPNNNN_O01 | Process Before Output.                                                                                                                                                                                  |
| ZMMTPNNNN_I01 | Process After Input.                                                                                                                                                                                    |
| ZMMTPNNNN_CLS | Definición de clases locales e implementación de todos los métodos de <br/>una clase                                                                                                                    |

## 3.5 Creación de Grupo de Funciones

Los nombres correspondientes al grupo de Función serán de la siguiente forma 
**ZGFAAA_NNN**.

- **Z** Por definición SAP
- **GF** Constante que identifica el Grupo de Funciones 
- **AAA** Módulo SAP o proyecto
- **NNN** Número consecutivo 
  
Se debe tener en cuenta que es preferible un grupo de funciones para una funcionalidad en 
específico. 

- **ZGFAAA_001** Grupo de Funciones para Consultas
- **ZGFAAA_002** Grupo de Funciones para conversión de datos

## 3.6 Creación de Módulos de Función

Los nombres correspondientes al módulo de Función serán de la siguiente forma 
**ZFAAA_XXX_VNN**. 

- **Z** Por definición SAP 
- **F** Constante que identifica el Modulo de Funciones 
- **AAA** Módulo SAP o proyecto
- **XXX** Descripción literal de la funcionalidad 
- **VNN** Versión de la Función (Esta nomenclatura es opcional) 

## 3.7 Creación Tabla

Los nombres de estos objetos tendrán la siguiente forma **ZTAAA_[X…X]**

- **Z** Por definición SAP 
- **T** Constante que identifica el que es una Tabla 
- **AAA** Módulo SAP o proyecto
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:** ZTAAA_EJEMPLO

## 3.8 Creación Vista

Los nombres de estos objetos tendrán la siguiente forma **ZVAAA_[X…X]**

- **Z** Por definición SAP 
- **V** Constante que identifica el que es una Vista 
- **AAA** Módulo SAP o proyecto
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:** ZVAAA_EJEMPLO


## 3.9 Creación Estructura

Los nombres de estos objetos tendrán la siguiente forma **ZSAAA_[X…X]**

- **Z** Por definición SAP 
- **S** Constante que identifica el que es una estructura 
- **AAA** Módulo SAP o proyecto
- **XXX** Descripción literal de la funcionalidad (Separado por _) 

**Ejemplo:** ZSAAA_EJEMPLO

### 3.9.1 Estructura Append

Los nombres de estos objetos tendrán la siguiente forma **ZZSAAA_[X…X]** 

>Nota: Los nombres de los campos deberán empezar con **ZZ**. 

## 3.10 Creación Tipo Tabla

Los nombres de estos objetos tendrán la siguiente forma **ZTTAAA_[X...X]**

- **Z** Por definición SAP 
- **TT** Constante que identifica el que es un Tipo tabla 
- **AAA** Módulo SAP o proyecto
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:** ZTTAAA_EJEMPLO.

## 3.11 Creación Elemento De Datos

Los nombres de estos objetos tendrán la siguiente forma **ZE_[X…X]**

- **Z** Por definición SAP 
- **E** Constante que identifica el que es un Elemento de Dato 
- **AAA** Módulo SAP o proyecto **(Opcional)**
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:** ZEAAA_EJEMPLO


## 3.12 Creación de Dominio

Los nombres de estos objetos tendrán la siguiente forma **ZD_XXX**

- **Z** Por definición SAP 
- **D** Constante que identifica el que es un Dominio
- **AAA** Módulo SAP o proyecto **(Opcional)**
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:**
ZD_CHAR Almacena un texto de 10 caracteres 
ZD_DEC Almacena un número de longitud 13 y 2 decimales.

### 3.12.1 Los dominios con ámbito de valores

Los nombres de estos objetos tendrán la siguiente forma **ZDAV_XXX**

- **Z** Por definición SAP
- **D** Constante que identifica el que es un Elemento de Dato 
- **AV** Constante que identifica el que es un Ámbito de valor 
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
  
**Ejemplo:** ZDAV_EJEMPLO

## 3.13 Creación Ayuda de Búsqueda

Los nombres de estos objetos tendrán la siguiente forma **ZH_XXX**

- **Z** Por definición SAP 
- **H** Constante que identifica el que es una Ayuda de Búsqueda 
- **AAA** Módulo SAP o proyecto **(Opcional)**
- **XXX** Descripción literal de la funcionalidad (Separado por _) 
 
 **Ejemplo:** ZH_EJEMPLO 

## 3.14 Clase De Mensaje 

Los nombres de las clases de mensaje tienen la siguiente forma **ZMAAA_NNN**. 

- **Z** Por definición SAP 
- **M** Constante que identifica el que es una clase de Mensaje 
- **AAA** Módulo de Aplicación 
- **NNN** Correlativo de 3 dígitos 
  
**Ejemplo:** ZMAAA_001

# 4. Modificaciones

Todo programa desarrollado debe incluir comentarios, con el propósito de facilitar a futuros 
programadores una mejor comprensión del código desarrollado y disminuir el impacto que 
representa para esta persona la modificación de un código no propio. Todo comentario debe 
estar en letra minúscula, además debe ser claro y conciso, dando una idea general de la función 
que realiza esa sección de código en el programa.

## 4.1 Encabezado

La cabecera de un programa ABAP debe respetar el siguiente formato:

```abap
 ************************************************************************ 
*& Nombre del Objeto: *
*& Tipo Objeto (Transacción, Programa, Modulo de Función etc). * 
*& Aplicación (Módulo o proyecto) *
*& Funcional *
*& Desarrollador *
*& Fecha Creación: * 
*& Descripción: *
* *********************************************************************** 
*& MODIFICACIONES *
************************************************************************* 
*& ID: @NNN *
*& Funcional *
*& Desarrollador *
*& Orden de Transporte *
*& Fecha Modificación *
*& Motivo *
************************************************************************
```

> NOTAS. 
- Todo programa principal deberá tener un encabezado en las primeras líneas del código 
fuente. (de no tenerlo se debe crear con la básica que se cuente).
- La sección **MODIFICACIONES** debe actualizarse siempre que se haga un ajuste en el 
código fuente.
- **ID**, este consecutivo es el identificador de cada modificación, tiene una longitud de 3 
caracteres, se debe colocar al inicio y final de la modificación. En caso de ser una sola línea 
se debe adicionar al final de ella.
- **Motivo**, Se debe realizar la descripción de cuál es el ajuste que se realizó a la 
funcionalidad.

## 4.2 Comentario Línea

Debe contener el número de modificación y la descripción de la funcionalidad de esa sección de código.

**“@NNN Texto Explicativo**

**Ejemplos.**

- Agregar una línea de código 
  
```abap
DATA: ls_ipm_autor TYPE /ibmishc/ipm_010 "@001 Se inserta Work 
Area
```

- Modificar una línea de código 
  
```abap
ASSIGN ls_tvalor TO <fs_tvalor>. "@001 Se reemplaza variable de 
asignación
```

- Eliminar/Comentar una línea de código 

```abap
"ASSIGN ls_ipm011 TO <fs_ipm011>. "@001 Se elimina Asignación a 
Field Symbol
```

>Notas.
- Cuando se agregan, modifican o comentan varias líneas de código, se debe identificar el 
principio y fin del ajuste. 

# 5. Declaración de datos globales

Para la declaración de las constantes y variables globales utilizadas en el programa o módulo de 
función se debe guiar por el siguiente formato:


## 5.1 Declaración de Tablas

Para la declaración de tablas se debe tener en cuenta la siguiente plantilla.

>***Nota:*** *En frente de cada declaración de tabla se debe colocar la descripción*

```abap
**************************************************************
*** Declaración de tablas 
************************************************************** 
TABLES: Nombre_tabla. “Breve descripción de la tabla
Ejemplo:
TABLES: T001W, "Centros/Sucursales 
 MBEW, "Valoración de material 
 MSEG. "Segmento doc.material 
```

## 5.2 Declaración variable

Para la declaración de variables se debe tener en cuenta que esta sección es dividida de la 
siguiente manera. 

### 5.2.1 Types

Descripción de tipo 

```abap
**************************************************************
*** Definición de tipos
************************************************************** 
TYPES: BEGIN OF gty_makt,
 matnr TYPE makt-matnr,
 maktx TYPE makt-maktx, 
END OF gty_makt,
gtt_makt TYPE TABLE OF gty_makt.
```

**Recomendaciones:**

- Para los objetos TYPES, Como son estructuras creadas dentro del programa, se 
recomienda que sean declaradas de manera global, en el TOP. Para poder ser 
reutilizada en cualquier momento. 

### 5.2.2 Tablas Internas

```abap
**************************************************************
*** Definición de tablas internas 
************************************************************** 
DATA: <Variable>_<nombre> TYPE <Objeto tipo tabla>, 
 <Variable>_<nombre> TYPE STANDARD TABLE OF <Objeto estructura>.
```

Donde: 
- \<Variable>: Corresponde a si es una variable global (GT), o variable 
local (LIT).
- \<nombre> Describe la funcionalidad de la tabla interna. 
- \<Objeto tipo tabla> Hace referencia a que debe tener propiedad tipo
tabla. 
- \<Objeto estructura> Hace referencia a que el objeto declarado debe tener 
propiedad de estructura de datos, tabla transparente o un objeto Types declarado 
previamente, esto para poder obtener la propiedad de la tabla. 

**Recomendaciones:**

- Los objetos TYPES, preferiblemente deben ser declarados en el TOP, declararlos 
como Estructuras y tipo tabla. 
- Variables globales declararlas en el TOP, y garantizar que cuando se vayan a 
utilizar las variables estén limpias.

### 5.2.3 Declaración Work Area

```abap
**************************************************************
*** Definición de estructuras 
************************************************************** 
DATA: <Variable>_<nombre> TYPE <Estructura>. 
```

Donde:
- \<Variable> Corresponde a si es una variable global (GWA), o variable local 
(LWA).
- \<nombre> Describe la funcionalidad del work área. 
- \<Estructura> Referencia a la estructura o TYPES (Creado en el TOP, previamente).
  
**Recomendaciones:**

- Variables globales declararlas en el TOP.
- Garantizar que cuando se vayan a utilizar las variables estén limpias. 

### 5.2.4 Declaración Field-symbols

```abap
**************************************************************
*** Definición de Field-symbols
************************************************************** 
FIELD-SYMBOLS: <Nombre_Field>.
```

Donde:

- Nombre_Field: nombre que exprese la funcionalidad del field-symbol, debe ir en <>.

### 5.2.5 Declaración Constantes

Para las constantes cuando son de manera global debe tener el sufijo **GC_XXX**

**G** -> Global 
**C** -> Constante 
**XXX** -> Descripción 

```abap
**************************************************************
*** Definición de Constantes
************************************************************** 
CONSTANTS: GC_constante TYPE n VALUE '<valor>'. “Descripción de la constante
```

Donde:
- \<Variable> Corresponde a si es una variable global (GC), o variable local (LC).
- \<nombre> Describe la funcionalidad de la constante. 
- \<valor> Corresponde al valor constante que va tener la variante 

### 5.2.6 Rangos

Para los rangos si son utilizados de manera global o local se utiliza el sufijo **GR_XXX** o 
**LR_XXX** respectivamente.

En caso de los work area se utiliza GWA o LWA haciendo referencia al rango 
correspondiente. 

```abap
**************************************************************
*** Definición de Rangos
************************************************************** 
DATA: gr_<nombre> TYPE RANGE OF BKPF-BUKRS, "rango de 
 gwa_<nombre> LIKE LINE OF GR_<NOMBRE>.
 ```

Donde:

- \<nombre> Describe la funcionalidad del rango. 
  
**Recomendaciones:**

- Al declarar la variable se debe hacer referencia a un elemento de datos definido en 
el diccionario de datos.
- Las declaraciones de variables globales se debe realizar en el TOP. 
- Declaraciones de variables locales se deben realizar en las líneas iniciales de la 
funcionalidad. 
