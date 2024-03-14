[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/VCT2iNTV)
#  Examen UD5. Validación para documentos XML.

Clona este repositorio y sigue las instrucciones. Al finalizar actualiza este mismo repositorio con los ficheros generados y **debidamente refenciados** en este mismo README.
- Añade un comentario con tu nombre completo al principio de cada fichero.
- En el XML deja entre comentarios aquellos datos no válidos que has usado para realizar pruebas o que has tenido que modificar.
- Usa como herrmientas específicas
   - Visual Studio
   - XML Copy Editor  
   - PROHIBIDO EL USO DE CUALQUIER MATERIAL ajeno a estas herramientas

RA4. Criterios de evaluación:
- Ce-d. Se han creado descripciones de documentos XML.
- Ce-e. Se han utilizado descripciones en la elaboración y validación de documentos XML.
- Ce-f. Se han asociado las descripciones con los documentos.
- Ce-g. Se han utilizado herramientas específicas.
- Ce-h. Se han documentado las descripciones.

## Ejercicio 1. 
Añade los siguientes elementos y atributos XML al fichero [ej1-JorgePradillo.xml](./ej1-jorgePradillo.xml). Escribe un [ej1-JorgePradillo.dtd](./ej1-jorgePradillo.dtd) válido para ellos con las siguientes restricciones. 

a. Si no se especifica el valor de base el valor es "1"
```xml
<triangulo base="100" />
```

b. El atributo número es obligatorio.
```xml
<mascota numero="5677" />
```

c. El atributo nombre es el valor fijo.
```xml
<centro_educativo nombre="IES Gran Capitán" />
```

d. El atributo tipo puede tener los valores cheque, tarjeta, efectivo
```xml
<abono tipo="cheque">30,4</abono>
```

## Ejercicio 2.
Corrige sin cambiar el DTD 

Entrega el ejercicio con nombre [ej2-JorgePradillo.xml](./ej2-JorgePradillo.xml) con las correcciones y los comentarios que indiquen el motivo de la corrección.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE alumno [
   <!ELEMENT alumno (edad, nombre, activo?)>
   <!ELEMENT edad (#PCDATA)>
   <!ELEMENT nombre (#PCDATA)>
   <!ELEMENT activo EMPTY>
]>

<alumno>
  <nombre>Emiliana Piedra</nombre>
  <edad>35</edad>
</alumno>
```


## Ejercicio 3. 
Escribe un xml válido para el siguiente DTD interno, con 3 libros y 5 préstamos. Entrega ejercicio con nombre [ej3-JorgePradillo.xml](./ej3-JorgePradillo.xml)

```xml
<!ELEMENT biblioteca (libro+,prestamo+)>
<!ELEMENT libro (titulo,autor)>
<!ATTLIST libro id NMTOKEN #REQUIRED>
<!ELEMENT titulo (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ELEMENT prestamo (fecha)>
<!ATTLIST prestamo idref NMTOKEN #REQUIRED>
<!ELEMENT fecha (#PCDATA)>
```

## Ejercicio 4 (por clonación). 
Por clonación, escribe en xml Schema [ej4-JorgePradillo.xsd](./ej4-JorgePradillo.xsd) la definición para los siguientes datos 

-  Un atributo obligatorio de nombre "importante" que tenga un valor booleano, por defecto, el valor es false. 

-  Un elemento proyecto que solo pueda tener los valores "en_progreso", "completo" y "pendiente" y por defecto el valor sea "en_progreso". 
-  Define un tipo de dato personalizado para el elemento película 
```xml
<pelicula anno="2023">
   <título>Oppenheimer</título>
   <nacionalidad>Reino Unido</nacionalidad>
   <clasificación>+12</clasificación>
</pelicula>
```
   -  El año no es obligatorio.

   -  El orden en el que aparecen los datos título, nacionalidad y clasificación puede ser cualquiera.
   
Entrega también el fichero [ej4-JorgePradillo.xml](./ej4-JorgePradillo.xml) que lo corrobore

## Ejercicio 5. 
Define un xml Schema [ej5-JorgePradillo.xsd](./ej5-JorgePradillo.xsd) para el siguiente fichero xml [ej5-JorgePradillo.xml](./ej5-JorgePradillo.xml) y añade los datos necesarios al fichero xml para que el fichero de
validación sea el xsd generado. 

```xml
<productos>
   <producto codigo="12345">
      <descripcion>Tipo A</descripcion>
      <cantidad>3</cantidad>
   </producto>
   <producto codigo="98765">
      <descripcion>Tipo B</descripcion>
      <cantidad>5</cantidad>
   </producto>
   <producto codigo="54321">
      <descripcion>Tipo C</descripcion>
      <cantidad>2</cantidad>
   </producto>
</productos>
```
Debes tener en cuenta:

- Productos tendrá al menos 1 o muchos elementos producto.

- El código es un atributo obligatorio de 5 dígitos.



