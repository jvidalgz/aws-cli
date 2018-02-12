# Comandos aws-cli
## S3
### s3api vs aws s3

La diferencia entre los comandos s3api y s3 es que los comandos s3 no están unicamente guiados por modelos JSON. 
Si no que, los comandos s3 están construidos sobre las operaciones encontradas en los comandos s3api. 
Como resultado, estos comandos permiten características de alto nivel que no son entregadas por los comandos s3api. 
Esto incluye, pero no se limita a, la capacidad para sincronizar directorios locales y buckets S3, 
transferir multiples archivos en paralelo, stream de archivos y automaticamente manejar trasferencias multiparte. 
En resumen estos comandos simplifican aun más y aceleran la transferencia de archivos hacia, dentro, y desde S3.


#### aws s3api ([documentacion](https://docs.aws.amazon.com/cli/latest/reference/s3api/index.html))
##### Buckets
* Crear bucket ([documentacion](https://docs.aws.amazon.com/cli/latest/reference/s3api/create-bucket.html))

```
aws s3api create-bucket --bucket my-bucket --region us-east-1
```
salida
```
{
    "Location": "/my-bucket"
}
```

##### Objetos



#### aws s3
##### Objetos
###### Elimina todos los objetos del bucket
--recursive (boolean) El comando es ejecutado sobre todos los archivos u objetos bajo el directorio o prefijo especificado.
```
aws s3 rm s3://mybucket --recursive
```
Salida
```
delete: s3://mybucket/15a7f6c350ff6c.mp4
delete: s3://mybucket/15a7f7e68283b8.mp4
```
##### Subir Objeto
```
aws s3api put-object --bucket mybucket --key default.jpg --body default.jpg --content-type "image/jpeg"

```