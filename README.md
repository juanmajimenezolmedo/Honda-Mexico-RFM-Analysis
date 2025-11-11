# Análisis RFM para la estrategia de retención de Honda en México durante la crisis de semiconductores 
## _La finalidad de este escrito pasa por la aplicación de un análisis RFM fundamentado en una estrategia de retención y pivote frente a la crisis de producción de 2025._

## 1. Problema de negocio

**Establecida en México desde 1985**, la factoría de Honda en Celaya (Guanajuato) se ha visto salpicada por la **disputa entre China y Países Bajos por el control de Nexperia**, que ha derivado en el cese de suministración de chips a empresas de automoción a nivel mundial.

En adición a esto, a nivel individual la marca teme tener que hacer frente a una serie de **consecuencias directas e inmediatas**:

  1) **Descenso crítico en el número de vehículos disponibles en inventario**.
  2) **Drástica bajada de los ingresos por ventas**.
  3) **Riesgo de fuga de clientes hacia marcas competidoras con mayor oferta de producto** (Toyota, Nissan o Kia, entre otras).

Frente a la incógnita de **cómo puede Honda generar ingresos y mantener la lealtad de sus consumidores** ante la barrera que supone no poder vender automóviles, se ha optado por la aplicación de un cambio de paradigma.

Y es que la marca ha de reorientar su enfoque de negocio de "vender autos de primera mano" a "ofrecer servicios de postventa y retención excelsos". Premisa bajo la cual el **análisis de RFM** entra en acción.

## 2. Aplicación del modelo RFM

### 2.1. Fuente de procedencia del dataset

En una situación ideal, contar con los datos transaccionales reales de los clientes de Honda nos hubiese puesto más en tesitura con la realidad de la marca. Ante la imposibilidad de contar con ellos dada su privacidad, se ha optado por la **generación de un dataset sintético**.

Este conjunto de datos, creado mediante **Python** (**Pandas** y **Numpy**), simula de forma realista el historial de transacciones del taller de postventa. Nos encontramos pues con un total de [Tu número, ej: 45,000] transacciones de [Tu número, ej: 5,000] clientes en un período de [Tu número, ej: 3] años, el cuál se halla estructurado en tres columnas clave:

  1) **CustomerID:** El identificador único del propietario del vehículo.
  2) **TransactionDate:** La fecha en la que el cliente acudió al servicio.
  3) **Amount:** El gasto total de esa visita (incluyendo servicio y repuestos).

Este enfoque nos permite aplicar el modelo RFM en **un entorno controlado pero realista**, que refleja los **distintos comportamientos** de los consumidores.

## 3. Segmentación de clientes y acciones de marketing 

## 4. Datos y herramientas necesarias
