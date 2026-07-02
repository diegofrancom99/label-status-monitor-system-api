# Label Status Monitor System API

System API desarrollada con MuleSoft para consultar el estado de etiquetas (Label Status) desde una base de datos PostgreSQL.

---

## Tecnologías

- MuleSoft 4
- APIKit
- DataWeave 2.0
- PostgreSQL
- CloudHub 2.0
- API Manager

---

## Arquitectura

La solución sigue una arquitectura API-led.

```text
Request
    │
    ▼
Orchestrator
    │
    ▼
Client
    │
    ▼
PostgreSQL
```

---

## Características

- Consulta por:
  - Plant
  - Resource
  - Order
- Respuesta con múltiples registros.
- Manejo de errores personalizado (404).
- Configuración externalizada mediante YAML.
- Despliegue en CloudHub 2.0.
- Administración mediante API Manager.
- API Autodiscovery.
- Seguridad mediante Client ID Enforcement.

---

## Ejemplo de Request

```json
{
  "plant": "MDBN",
  "resource": "LINEA007",
  "order": "10001590"
}
```

---

## Ejemplo de Response

```json
{
  "plant": "MDBN",
  "resource": "LINEA007",
  "order": "10001590",
  "HU_Container": [
    {
      "Plant": "MDBN",
      "Resource": "LINEA007",
      "ProcessOrder": "10001590"
    }
  ]
}
```

---

## Flujo de despliegue

1. Diseño del RAML.
2. Publicación en Exchange.
3. Despliegue en CloudHub 2.0.
4. Registro de la instancia en API Manager.
5. Configuración de API Autodiscovery.
6. Aplicación de Client ID Enforcement.
7. Pruebas desde Postman.

---

## Lecciones aprendidas

- Diseño de una System API utilizando API-led Connectivity.
- Separación de responsabilidades entre Client y Orchestrator.
- Uso de DataWeave para transformaciones técnicas.
- Externalización de propiedades mediante YAML.
- Despliegue en CloudHub 2.0.
- Administración de APIs con API Manager.
- Configuración de API Autodiscovery.
- Implementación de Client ID Enforcement.
- Pruebas end-to-end utilizando Postman.

---

## Arquitectura de Seguridad

La API utiliza la política **Client ID Enforcement** administrada desde API Manager.

El acceso requiere:

- client_id
- client_secret

Las políticas son aplicadas mediante **API Autodiscovery**, permitiendo administrar la seguridad sin modificar el código de la aplicación.

---

## Autor

**Diego Franco**