# Trabajo Grupal XML 1

## Descripción
Este repositorio contiene archivos XML que simulan un **Sistema de reservas de un hotel**. 
Consta de un archivo XML que utiliza la estructura definida en los archivos **DTD y XSD**, los cuales establecen los apartados que debe contener el documento XML.

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
El archivo datos.xml tiene como elemento raíz `hotel`, que contiene una o varias reservas.
Cada `reserva` representa una reserva individual y está identificada mediante un atributo obligatorio.

Dentro de cada reserva se incluyen dos elementos principales:

- `habitacion` : contiene la información de la habitación reservada.

- `persona` : contiene la información del cliente que realiza la reserva.

La estructura jerárquica permite agrupar correctamente los datos y mantener una organización clara y coherente.

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
El documento DTD define la estructura lógica del XML mediante las declaraciones `<!ELEMENT>` y `<!ATTLIST>`, que indican qué elementos pueden aparecer, en qué orden y qué atributos son obligatorios.

El elemento raíz `<hotel>` se declara como contenedor del resto de elementos, las secciones principales son: `<reserva>`, lo que se indica mediante el símbolo *, permitiendo que existan una o más de una reserva.

Cada `<reserva>` está compuesta por dos elementos principales: `<habitacion>` y `<persona>`, definidos en un orden concreto, lo que obliga al XML a respetar dicha jerarquía.

El elemento `<habitacion>` incluye el subelemento `<planta>`, que contiene texto `(#PCDATA)`, y un atributo obligatorio numero, definido mediante `<!ATTLIST>` con la opción `#REQUIRED`.

El elemento `<persona>` agrupa los datos personales del cliente y contiene los subelementos `<nombre>`, `<telefono>`, `<e-mail>`, `<fecha_entrada>` y `<fecha_salida>`, todos definidos como texto. Además, dispone del atributo obligatorio DNI, que identifica de forma única a la persona.

De este modo, el DTD controla la estructura, el orden de los elementos de los atributos, garantizando que el documento XML sea válido desde el punto de vista estructural.

## Qué valida el XSD
El documento XSD define la estructura del XML utilizando etiquetas propias de XML Schema, lo que permite una validación más detallada que el DTD.

El esquema comienza con la definición del elemento raíz `<xs:element name="hotel">`, que contiene un elemento complejo `(<xs:complexType>)`, ya que incluye otros elementos en su interior.
Dentro de este elemento se utiliza `<xs:sequence>` para indicar que los elementos de dentro deben aparecer en un orden específico.

El elemento `<reserva>` se define como un elemento repetible mediante el atributo `maxOccurs="unbounded"`, lo que permite que el documento XML contenga múltiples reservas. Cada reserva se define también como un elemento complejo que agrupa los elementos `<habitacion>` y `<persona>`.

Los elementos `<habitacion>` y `<persona>` se definen como complejos, ya que contienen subelementos y atributos. En ambos casos se utiliza `<xs:sequence>` para establecer el orden de los elementos internos.

En el caso de `<habitacion>`, se define el subelemento `<planta>` con tipo `xs:string`, y se declara el atributo numero como obligatorio mediante `use="required"`.
En el caso de `<persona>`, se definen los subelementos `<nombre>`, `<telefono>`, `<e-mail>`, `<fecha_entrada>` y `<fecha_salida>`, asignándoles tipos de datos como `xs:string` y `xs:integer`. Además, se declara el atributo obligatorio DNI.

Gracias a esta estructura, el XSD permite validar no solo la jerarquía y el orden de los elementos, sino también los tipos de datos, la repetición de elementos y la obligatoriedad de los atributos, asegurando una validación más completa del documento XML.

## Dificultades encontradas durante el desarrollo
La mayor dificultad que hemos encontrado durante el desarrollo del proyecto ha sido terminar de afianzar los conceptos recientemente aprendidos relacionados con estos tres tipos de documentos
y el planteamiento de la estructura para que fuera funcionalmente adecuada a las características requeridas por el proyecto

## División del trabajo
- **Laura** archivo XSD y README
- **Noemí** archivo DTD y XML

## Autores

- Laura Otero Martín
- Noemí Cano Conesa