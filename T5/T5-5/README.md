# UD5 A5. Validación. Conceptos

1. **Indica con una X las afirmaciones verdaderas:**

- [ ] Los DTDs son más ricos y poderosos que los XML Schemas

- [ ] Los DTDs están escritos de acuerdo a la sintaxis XML

- [x] XML Schemas soportan tipos de datos

- [x] XML Schemas soportan namespaces
- [ ] XML Schemas tienen el nodo raíz schema con la URL que contiene la definición de todos los elementos y atributos que se pueden utilizar en un esquema. Eso quiere decir que para programar en XML se necesita estar conectado a Internet.
- [x] En XSD, el atributo xmlns crea un espacio de nombres para cada URL referenciada. Así si hubiese dos elementos con el mismo nombre se diferencian claramente.



2. A continuación aparece la declaración de un esquema XSD. Indica los siguientes elementos:

- prólogo. Define la versión del lenguaje XML y el juego de caracteres utilizado

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  ```

- prefijo del espacio de nombres (opcional)

  ```
  xs
  ```

- espacio de nombres XMLSchema
  ```
  xmlns:xs="http://www.w3.org/2001/XMLSchema"
  ```
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema 
    xmlns:xs="http://www.w3.org/2001/XMLSchema">
		...
<xs:schema />
```

3. A continuación aparece la vinculación de un esquema a un documento XML. Indica (con una X) si está en nuestro sistema de ficheros local o es un esquema público.

- [X] esquema local

- [ ] esquema público
```xml
<factura num="num_fact_1234"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="factura.xsd">
	...
</factura>
```

- [ ] esquema local

- [X] esquema público
```xml
<factura num="num_fact_1234"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.miempresa.com/factura.xsd">
...
</factura>	
```
  
4. De los siguientes tipos predefinidos por el espacio de nombres XMLSchema del W3C, marca con una X los numéricos:
- [ ] normalizedString
- [ ] dateTimeStamp
- [ ] language
- [ ] IDREFS
- [ ] dayTimeDuration
- [ ] NMTOKEN
- [ ] NMTOKENS
- [ ] Name
- [ ] NCName
- [ ] ID
- [ ] IDREF
- [ ] ENTITY
- [X] integer
- [ ] yearMonthDuration
- [X] nonPositiveInteger
- [X] negativeInteger
- [X] long
- [X] int
- [X] short
- [X] byte
- [ ] token
- [X] nonNegativeInteger
- [X] unsignedLong
- [X] unsignedInt
- [ ] ENTITIES
- [X] unsignedShort
- [X] unsignedByte
- [X] positiveInteger

5. Adjunta un [fichero .xsd](./ficheroXSD.xsd) con el siguiente diseño:
```xml
<!-- definición de elementos simples -->
<!-- definición de atributos -->
<!-- definición de elementos  complejos -->
<!-- definición de los tipos simples -->
<!-- definición de los tipos complejos -->
<!-- elemento raíz -->
```

6. Con respecto a la validación con XSD indica:
- Un esquema es un documento *XML* al que se le coloca la extensión **.xsd**. Al ser un archivo XML tiene la estructura habitual de todo documento XML con la obligación de que el elemento **raíz** se llame **&lt;xsd:schema&gt;** .
- Etiqueta que identifica la raíz de un documento XML Schema: 
- Etiquetas que identifican las partes de un esquema:
  - Elementos, definidos con etiquetas **&lt;xs:element&gt;**. Para indicar los elementos permitidos en los documentos que sigan el esquema.
  - Atributos, etiqueta **&lt;xs:attribute&gt;**.
  - Tipos simples, que permiten definir los tipos simples de datos que podrá utilizar el documento XML. Lo hace la etiqueta **&lt;xs:simpleType&gt;** .
  - Tipos complejos, mediante la etiqueta **&lt;xs:complexType&gt;**
  - Documentación, información utilizable por aplicaciones que manejen los esquemas. Etiquetas **&lt;xs:anotation&gt;** y **&lt;xs:documentation&gt;**.
- Componentes locales y globales en un esquema:
  - En ámbito **global**. Se trata de los elementos del esquema que se coloquen dentro de la etiqueta raíz schema y que no están dentro de ninguna otra. Estos elementos se pueden utilizar en cualquier parte del esquema.
  - En ámbito **local**. Se trata de elementos definidos dentro de otros elementos. En ese caso se pueden utilizar sólo dentro del elemento en el que están inmersos y no en todo el documento. Es decir si, por ejemplo, si dentro de la definición de un atributo colocamos la definición de un tipo de datos, este tipo de datos sólo se puede utilizar dentro del elemento xs:attribute en el que se encuentra la definición del tipo de datos.
- Dentro de la etiqueta xs:element, indica:
  - atributos obligatorios
  - atributos optativos

7. Definición de un elemento vacío en XSD
  
Un elemento vacío es uno que no tiene contenido, es decir, no contiene subelementos ni datos. En XML Schema, puedes definir elementos con contenido o elementos vacíos utilizando el elemento **&lt;element&gt;**.

Un ejemplo de un elemento vacío en XSD podría ser algo así:

  ```xml
  <xs:element name="elementoVacio" type="xs:string"/>
  ```
  
En este ejemplo, se define un elemento llamado "elementoVacio" que tiene un tipo de datos de cadena (xs:string). Este elemento no tiene restricciones adicionales y no tiene contenido interno, por lo que se consideraría un elemento vacío.


De interés
- https://jorgesanchez.net/manuales/xml/xml-validacion.html
- https://www.w3schools.com/xml/el_restriction.asp
- https://lm-xml-apuntes.readthedocs.io/apuntes/40_esquemas_xml.html#tipos-de-elementos
