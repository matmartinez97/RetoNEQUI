# Prueba tecnica NEQUI - Científico de datos

Este repositorio contiene el código del modelo que busca encontrar transacciones atípicas por su frecuencia.

**El modelo consiste de un calculo de RFM por cuenta, clusterización de cuentas con RFM similares, comparación de transacción nueva con los centroides del cluster y toma de decisiones basada en los Z-Score.**

## Arquitectura propuesta para el modelo

A continuación se muestra una imagen de la arquitectura que se propone para la puesta en producción del modelo utilizando componentes de AWS.

![Arquitectura](Arquitectura.png)

Notemos que al final el modelo termina en una base de datos relacional puesto que es una tabla con la cual podremos hacer las comparaciones.
