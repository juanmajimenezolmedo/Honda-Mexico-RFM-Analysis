# Análisis RFM para la estrategia de retención de Honda en México durante la crisis de semiconductores 

## _La finalidad de este escrito pasa por la aplicación de un análisis RFM fundamentado en una estrategia de retención y pivote frente a la crisis de producción de 2025._

## 1. Problema de negocio

Establecida en México desde 1985, la factoría de Honda en Celaya (Guanajuato) se ha visto salpicada por la disputa entre China y Países Bajos por el control de Nexperia, que ha derivado en el cese de suministración de chips a empresas de automoción a nivel mundial.

En adición a esto, a nivel individual la marca teme tener que hacer frente a una serie de consecuencias directas e inmediatas:

1) **Descenso crítico en el número de vehículos disponibles en inventario**.
2) **Drástica bajada de los ingresos por ventas**.
3) **Riesgo de fuga de clientes hacia marcas competidoras con mayor oferta de producto** (Toyota, Nissan o Kia, entre otras).

Frente a la incógnita de cómo puede Honda generar ingresos y mantener la lealtad de sus consumidores ante la barrera que supone no poder vender automóviles, se ha optado por la aplicación de un cambio de paradigma.

Y es que la marca ha de reorientar su enfoque de negocio de "vender autos de primera mano" a "ofrecer servicios de postventa y retención excelsos". Premisa bajo la cual el análisis de RFM entra en acción.

## 2. Aplicación del modelo RFM

### 2.1. Fuente de procedencia del dataset

En una situación ideal, contar con los datos transaccionales reales de los clientes de Honda nos hubiese puesto más en tesitura con la realidad de la marca. Ante la imposibilidad de contar con ellos dada su privacidad, se ha optado por la generación de un dataset sintético.

Este conjunto de datos, creado mediante Python (Pandas y Numpy), simula de forma realista el historial de transacciones del taller de postventa. Nos encontramos pues con un total de [Tu número, ej: 45,000] transacciones de [Tu número, ej: 5,000] clientes en un período de [Tu número, ej: 3] años, el cuál se halla estructurado en tres columnas clave:

1) **CustomerID:** El identificador único del propietario del vehículo.
2) **TransactionDate:** La fecha en la que el cliente acudió al servicio.
3) **Amount:** El gasto total de esa visita (incluyendo servicio y repuestos).

Este enfoque nos permite aplicar el modelo RFM en un entorno controlado pero realista, que refleja los distintos comportamientos de los consumidores.

### 2.2. Adaptación de las métricas RFM

El poder del modelo RFM radica en su simplicidad, pero su verdadero valor emerge al reinterpretar sus métricas para el problema específico de la postventa automotriz. Para este proyecto, las métricas se definen de la siguiente manera:

1) **R (Recencia):** _¿Cuán reciente fue la última visita del cliente al taller?_
  - **Medición:** Días transcurridos desde la última TransactionDate registrada hasta la fecha de análisis (11 de noviembre de 2025).
  - **Importancia:** Es el indicador más potente del engagement actual. Un cliente que vino hace 30 días está más "caliente" y receptivo que uno que no visita el taller oficial desde hace dos años, el cual se considera "frío" o en riesgo de fuga.

3) **F (Frecuencia):** _¿Qué tan a menudo el cliente utiliza los servicios oficiales de Honda?_
  - **Medición:** Número total de transacciones (visitas al taller) registradas para cada CustomerID.
  - **Importancia:** Separa a los clientes leales y habituales (que realizan todos sus mantenimientos en el concesionario) de aquellos clientes esporádicos o de una sola visita (que pudieron haber venido solo por el servicio de cortesía).

4) **M (Valor Monetario):** _¿Cuál es el gasto acumulado del cliente en el taller?_
  - **Medición:** Suma total de Amount (gasto) de todas las transacciones de un CustomerID.
  - **Importancia:** Identifica a los clientes más rentables. No es lo mismo un cliente que solo realiza el cambio de aceite básico, que uno que invierte en servicios premium, repuestos originales y accesorios.

### 2.3. Metodología de Puntuación y Segmentación

Tras el cálculo de estos tres valores (R, F y M) para cada cliente, procedemos a la extrapolación de estos hacia un sistema de medición comparable.

Para ello, se utilizará el método de cuartiles, donde cada cliente será clasificado en uno de cuatro grupos, con puntuaciones de 1 a 4 para cada una de las métricas. De esta manera, el 25% de clientes con la Recencia más baja (los que visitaron el taller más recientemente) recibirán una puntuación de 4, mientras que el 25% con la Recencia más alta (los que no han vuelto en más tiempo) recibirán un 1.

Al combinar las tres puntuaciones individuales, se crea un Score RFM para ese individuo (ej. "4-2-3" o "1-3-4"), pudiendo así agrupar a los clientes en segmentos de comportamiento determinados (como pueden ser "Clientes VIP", "Leales" o "En Riesgo de Fuga"), acción clave en la elaboración de una estrategia de retención, plasmada en apéndices venideros.

## 3. Segmentación de clientes y acciones de marketing 

## 4. Datos y herramientas necesarias
