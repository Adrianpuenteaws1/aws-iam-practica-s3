# aws-iam-practica-s3
Practica de IAM en AWS: control de acceso a S3 con politicas personalizadas
# AWS IAM - Control de acceso a S3

## Descripción

Práctica de implementación de control de acceso en Amazon S3 utilizando IAM en AWS, aplicando el principio de mínimo privilegio.

## Objetivo

Permitir que un usuario pueda visualizar y subir archivos únicamente en un bucket específico, evitando permisos innecesarios.

## Problema identificado

Al intentar subir un archivo a S3, se presentó el siguiente error:
Access Denied

## Análisis

El usuario contaba únicamente con permisos de lectura:

* s3:GetObject
* s3:ListBucket

No tenía permitido:

* s3:PutObject

## Solución implementada

Se creó una política personalizada con los siguientes permisos:

* s3:GetObject
* s3:ListBucket
* s3:PutObject

Restringiendo el acceso únicamente al bucket específico:

arn:aws:s3:::bucket-prueba-iam-adrian
arn:aws:s3:::bucket-prueba-iam-adrian/*

## Resultado

El usuario pudo subir archivos correctamente sin necesidad de otorgar permisos excesivos, manteniendo un control de acceso seguro.

## Aprendizajes

* Gestión de identidades con IAM
* Uso de políticas en formato JSON
* Resolución de errores de permisos
* Aplicación del principio de mínimo privilegio

## Herramientas utilizadas

* AWS IAM
* Amazon S3
* GitHub
