# CFDI
Librería java para la consulta de un estatus CFDI ante el SAT

##Cómo añadir la librería

###NetBeans

- Descarga el .jar
- Añádelo a tu proyecto dando clic derecho el la carpeta de librerías del proyecto y selecciona la opción Añadir JAR/FOLDER

![Cómo añadir la librería a NetBeans](https://github.com/AdolfoA98/CFDI/blob/main/screenshots/how%20to_netbeans.png)

##Cómo se utiliza

Esta librería está hecha para conocer el estado de las facturas ante el SAT utilizando la API proporcionada por la misma institución.

- La clase se llama ConsultaWeb, dentro del paquete CFDI
- El método para la consulta se llama consultaCFDI y se utiliza de la siguiente manera

```java
consulta.consultaCFDI("emisor", "receptor", "importe", "CFDI");
```

            El resultado contiene los siguientes campos
                - Cancelado - Boolean
                - CodigoEstatus - String
                - EsCancelable -  String
                - Estado - String
                - EstatusCancelacion - String
                - ExpresionErronea - String
                - Vigente  - Boolean

##Ejemplo de implementación

```java
package pruebacfdi;

import mx.gob.ssaver.cfdi.ConsultaWeb;
import mx.gob.ssaver.cfdi.modelos.ContenidoCFDI;

public class PruebaCFDI {

    public static void main(String[] args) {
        ConsultaWeb consulta = new ConsultaWeb();
        ContenidoCFDI contenido = consulta.consultCFDI("LSO1306189R5", "GACJ940911ASA", "4999.99", "e7df3047-f8de-425d-b469-37abe5b4dabb");
        System.out.println(contenido.getEstado());
        
    }
    
}
```

##Referencias

- [Developers-sw](https://developers.sw.com.mx/knowledge-base/servicio-publico-de-consulta-estatus-cfdi-sat/)
- [Tar.mx](https://tar.mx/archivo/2018/validar-folio-fiscal-cfdi-con-php-directo-del-sat-2018.html)
- [SAT](https://www.sat.gob.mx/consulta/71663/conoce-los-servicios-especializados-de-validacion) En esta liga se encuentra el manual en pdf (Web Service de Validación de CFDI)



