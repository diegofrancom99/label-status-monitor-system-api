\# Label Status Monitor System API



System API desarrollada con MuleSoft para consultar el estado de etiquetas (Label Status) desde una base de datos PostgreSQL.



\## Tecnologías



\- MuleSoft 4

\- APIKit

\- DataWeave 2.0

\- PostgreSQL

\- CloudHub 2.0

\- API Manager



\## Arquitectura



La solución sigue una arquitectura API-led.



```

Request

&#x20;   │

&#x20;   ▼

Orchestrator

&#x20;   │

&#x20;   ▼

Client

&#x20;   │

&#x20;   ▼

PostgreSQL

```



\## Características



\- Consulta por:

&#x20; - Plant

&#x20; - Resource

&#x20; - Order



\- Respuesta con múltiples registros.



\- Manejo de errores personalizado (404).



\- Configuración externalizada mediante YAML.



\- Despliegue en CloudHub 2.0.



\- Administración mediante API Manager.



\- API Autodiscovery.



\- Seguridad mediante Client ID Enforcement.



\## Ejemplo de Request



```json

{

&#x20; "plant": "MDBN",

&#x20; "resource": "LINEA007",

&#x20; "order": "10001590"

}

```



\## Ejemplo de Response



```json

{

&#x20; "plant": "MDBN",

&#x20; "resource": "LINEA007",

&#x20; "order": "10001590",

&#x20; "HU\_Container": \[

&#x20;   {

&#x20;     "Plant": "MDBN",

&#x20;     "Resource": "LINEA007",

&#x20;     "ProcessOrder": "10001590"

&#x20;   }

&#x20; ]

}

```



\## Flujo de despliegue



1\. Publicación en Exchange.

2\. Deploy en CloudHub 2.0.

3\. Registro en API Manager.

4\. Configuración de API Autodiscovery.

5\. Aplicación de la política Client ID Enforcement.

6\. Consumo desde Postman.



\## Autor



Diego Franco

