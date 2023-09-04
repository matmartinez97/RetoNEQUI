# Prueba tecnica NEQUI - Científico de datos

Este repositorio contiene el código del modelo que busca encontrar transacciones atípicas por su frecuencia.

**El modelo consiste de un calculo de RFM por cuenta, clusterización de cuentas con RFM similares, comparación de transacción nueva con los centroides del cluster y toma de decisiones basada en los Z-Score.**

## Arquitectura propuesta para el modelo

A continuación se muestra una imagen de la arquitectura que se propone para la puesta en producción del modelo utilizando componentes de AWS.

![Arquitectura](Arquitectura.png)

Notemos que al final, el resultado se guarda en una base de datos relacional puesto que nuestro modelo no arroja una función que permite clasificar sino que deja una tabla que nos sirve para hacer comparaciones.

## ¿Cada cuanto re-entrenar el modelo?

Según la información suministrada en el conjunto de datos, en promedio se realizan 64.421 transacciones al día, lo que equivale a unas 450.947 transacciones semanales. Si tenemos en cuenta que estamos trabajando únicamente con una muestra, el número de transacciones es aún mayor.

Con tanta información disponible, posibles patrones de comportamiento cambiantes para los clientes y considerando que el algoritmo no requiere un alto poder de cómputo, se podrian calcular nuevamente los valores de RFM y realizar la clusterización para cada grupo de cuentas **cada semana durante horas nocturnas y en días de bajo flujo transaccional, lo que permitiria no afectar otros procesos.**