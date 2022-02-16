# Lineamientos ABAP


- [1. Ordenes de transporte](#1-ordenes-de-transporte)
- [2.  Comentarios](#2--comentarios)
  - [2.1 Encabezado](#21-encabezado)
  - [2.2 Comentario Línea](#22-comentario-línea)
- [3. Convenciones](#3-convenciones)

# 1. Ordenes de transporte

Creación de OT con la nomenclatura


| Orden de transporte | MO NNN: BBB - DDD - VXXX | MO- Módulo <br/>NNN- Iniciales del Nombre del desarrollador<br/>BBB: Número del Caso <br/>DDD: Descripción caso <br/>XXX: Consecutivo con la versión empezando en 001 |
|---------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|

-	Comenzar con V01.
-	Aplica cuando se tenga más de una OT asociada al caso.
-	El transporte de órdenes a la ambiente calidad se debe realizar por **ordenes de transporte Copia** 

    * Se debe identificar con 



# 2.  Comentarios
## 2.1 Encabezado

-	Todo programa principal deberá tener un encabezado en las primeras líneas del código fuente. (de no tenerlo  se debe crear con la básica que se cuente).
-	La sección **MODIFICACIONES** debe actualizarse siempre que se haga un ajuste en el código fuente.
-	**ID**, este consecutivo es el identificador de cada modificación, tiene una longitud de 3 caracteres, se debe colocar al inicio y final de la modificación. En caso de ser una sola línea se debe adicionar al final de ella.


```abap

************************************************************************  
*& Nombre del Objeto:                                                   *
*& Tipo Objeto (Transacción, Programa, Modulo de Función etc).          * 
*& Aplicación (Módulo o proyecto)                                       *
*& Funcional                                                            *
*& Desarrollador                                                        *
*& Fecha Creación:                                                      * 
*& Descripción:                                                         *
* ***********************************************************************  
*& MODIFICACIONES                                                       *
*************************************************************************  
*& ID: @NNN                                                             *
*& Funcional                                                            *
*& Desarrollador                                                        *
*& Orden de Transporte                                                  *
*& Fecha Modificación                                                   *
*& Motivo                                                               *
 ************************************************************************
```



## 2.2 Comentario Línea

Debe contener el número de modificación y la descripción de la funcionalidad de esa sección de código. 

**"@NNN Texto Explicativo** 


# 3. Convenciones

Declaración de Objetos Globales

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

| **Tipo de objeto**         | **NOMENCLATURA**                                | **OBSERVACIONES**                                                                                                                                                                                                                                                                                                                                                   |
|------------------------|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Programa**               | ZRPMO_XXX                                   | **XXX** = Nombre que describa el desarrollo                                                                                                                                                                                                                                                                                                                         |
| **INCLUDE para  programa** | ZRP_AAA<br/><br/>**EJEMPLO.**<br/>ZRPMO_XXX_AAA | **AAA:** postfijo que indica el tipo de INCLUDE así:<br/>- **TOP** = Include con declaración de variables.<br/>- **EVE** = Include con declaración de eventos.<br/>- **RTN o F01** = Include con las rutinas del programa, etc.<br/>- **I01:** Eventos relacionados AFTER INPUT.<br/>- **O01:** Eventos relacionados BEFORE OUTPUT.<br/>- **CLS:** Eventos  con declaración de clases <br/> |
| **Grupo de función**       | ZFG_MO_XXX                                  |                                                                                                                                                                                                                                                                                                                                                                 |
| **Módulo de función**      | ZFM_MO_XXX                                  |                                                                                                                                                                                                                                                                                                                                                                 |
| **Transacción**            | ZMO_XXX                                     | Si el desarrollo tiene más de una transacción, debe agregarse ʺ_Nʺ<br/>**N:** consecutivo que inicie en 1.<br/>**Ejemplo**<br/>ZMOXXX_1<br/>ZMOXXX_2<br/>                                                                                                                                                                                                               |
| **Clases de mensajes**| ZMSG_MO_XXX                                 | Los parámetros se manejan con &1, &2, &3, &4                                                                                                                                                                                                                                                                                                                    |
| **Tabla**                  | ZTMO_XXX                                    |                                                                                                                                                                                                                                                                                                                                                                 |
| **Vistas**                 | ZV_MO_TABLA                                 | Tabla: Nombre de la tabla sin la letra 'Z'                                                                                                                                                                                                                                                                                                                      |
| **Tipo tabla**             | ZTTMO_XXX                                   |                                                                                                                                                                                                                                                                                                                                                                 |
| **Dominios**               | ZDM_MO_XXX                                  |                                                                                                                                                                                                                                                                                                                                                                 |
| **Elemento de datos**      | ZDEMO_XXX                                   |                                                                                                                                                                                                                                                                                                                                                                 |
| **Estructuras**            | ZSMO_XXX                                    |                                                                                                                                                                                                                                                                                                                                                                 |
| **Objetos Matchcode**      | ZMCMO_XXX                                   |                                                                                                                                                                                                                                                                                                                                                                 |
| **Paquete**                | ZPKGMO_XXX                                  |                                                                                                                                                                                                                                                                                                                                                                 |
| **Smartforms**             | ZSFMO_XXX                                   |                                                                                                                                                                                                                                                                                                                                                                 |
| **Estilos**                | ZSTMO_XXX                                   |                                                                                                                                                                                                                                                                                                                                                                 |
| **Clase**                  | ZCLMO_XXX                                   |
