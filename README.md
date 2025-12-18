# Trabajo Grupal XML 1

## Descripción
Este repositorio contiene archivos XML que simulan un **Sistema de reservas de un hotel**. COnsiste en un XML estructurado según una estructura establecida en un DTD y XSD que establecen los apartados que debe tener el XML.

```text
trabajo_XML/ 
├── datos.xml 
├── estructura.dtd 
├── esquema.xsd 
└── README.txt
```

## Contexto elegido
El tema elegido es un **Sistema de reservas de un hotel** en el que se especifíca la información relacionada con el usuario y las fechas, así como la habitación asignada. 

## Estructura del XML
La estructura es la siguiente:

```text
hotel 
├─ reserva 
├─── número de la reserva (obligatorio)
├─── habitación 
├────── número (obligatorio)
├────── planta
├─── persona
├────── DNI (obligatorio)
├────── nombre
├────── teléfono
├────── e-mail
├────── fecha de entrada
└────── fecha de salida 
```

## Qué valida el DTD
Para que el documento DTD valide correctamente el XML planteado debe tener la siguiente estructura: 


## Qué valida el XSD

## Dificultades encontradas durante el desarrollo

## División del trabajo
- **Laura** archivo XSD y README
- **Noemí** archivo DTD y XML

## Autores

- Laura Otero Martín
- Noemí Cano Conesa