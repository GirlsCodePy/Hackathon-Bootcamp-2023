## Datos de género correspondientes a empresas proveedoras del estado

Estos son los datos obtenidos del Portal de Datos Abiertos de la DNCP cuya documentación se encuentra disponible aquí:

https://contrataciones.gov.py/datos/def/Proveedor

Se agregó el campo gender como sigue:

```json
"details": {
        "gender": "male"
 }
```

El proceso para obtener este campo fue como sigue:

Se usó el campo `contactPoint.name`, que puede contener varios nombres con distintos tipos de separadores.

Se realizó la limpieza de datos, para separar los nombres de los diferentes representantes.

Por cada uno de estos representantes, se realizó una consulta a la api genderize.io para inferir si el nombre es masculino o femenino.

Si al menos la mitad más uno de los representantes corresponde a nombres femeninos, se asignó gender female a la empresa, caso contrario se asignó gender male.

## Disclaimer

Estos datos se generaron mediante inferencia de género por los nombres, puede haber errores puntuales.