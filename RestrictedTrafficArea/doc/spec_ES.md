Entidad: RestrictedTrafficArea  
==============================  
[Licencia abierta](https://github.com/smart-data-models//dataModel.Transportation/blob/master/RestrictedTrafficArea/LICENSE.md)  
Descripción global: **Zona de una ciudad en la que se limita el tráfico generado por los coches o cualquier otro tipo de vehículos.**  

## Lista de propiedades  

- `address`: La dirección postal  - `alternateName`: Un nombre alternativo para este artículo  - `areaServed`: La zona geográfica en la que se presta un servicio o se ofrece un artículo  - `category`: Categoría(s) de la zona de tráfico restringido. La finalidad de este campo es permitir etiquetar, en términos generales, las entidades de la zona de tráfico restringido. Las particularidades y descripciones detalladas se encuentran en los atributos específicos correspondientes.  - `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  - `dateCreated`: Marca de tiempo de creación de la entidad. Suele ser asignada por la plataforma de almacenamiento.  - `dateModified`: Marca de tiempo de la última modificación de la entidad. Normalmente será asignada por la plataforma de almacenamiento.  - `description`: Una descripción de este artículo  - `id`: Identificador único de la entidad  - `location`:   - `name`: El nombre de este artículo.  - `notAllowedVehicleType`: Tipo de vehículo(s) que no puede(n) cruzar la zona de tráfico restringido.  - `owner`: Una lista que contiene una secuencia de caracteres codificada en JSON que hace referencia a los identificadores únicos de los propietarios  - `regulation`: Una URL que apunte a la normativa de la zona específica de tráfico restringido.  - `restrictionExceptions`: Tipo de vehículo individual autorizado a cruzar la zona de tráfico restringido en una franja horaria determinada.  - `restrictionValidityHours`: Días de la semana y horas en las que la restricción de tráfico está activa.  - `security`: Aspectos de seguridad proporcionados por esta zona de tráfico restringido.  - `seeAlso`: lista de uri que apuntan a recursos adicionales sobre el artículo  - `source`: Una secuencia de caracteres que indica la fuente original de los datos de la entidad en forma de URL. Se recomienda que sea el nombre de dominio completo del proveedor de origen, o la URL del objeto de origen.  - `specialRestrictions`: Tipo de vehículo individual que no puede cruzar la zona de tráfico restringido en una franja horaria determinada.  - `type`: Tipo de entidad NGSI. Tiene que ser RestrictedTrafficArea  - `validityEndDate`: La fecha en la que se desestima la restricción.  - `validityStartDate`: La fecha a partir de la cual se aplica la restricción.    
Propiedades requeridas  
- `id`  - `type`    
Modelo de datos procedente del proyecto synchronicity  
## Descripción del modelo de datos de las propiedades  
Ordenados alfabéticamente (haga clic para ver los detalles)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
RestrictedTrafficArea:    
  description: 'An area of a city in which the traffic generated by cars or any other kind of vehicles is subjected to limitation.'    
  properties:    
    address:    
      description: 'The mailing address'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/addressCountry'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/addressLocality'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/addressRegion'''    
          type: string    
        areaServed:    
          description: 'Property. The geographic area where a service or offered item is provided. Model:''https://schema.org/areaServed'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, Spain. Model:''https://schema.org/postOfficeBoxNumber'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, Spain. Model:''https://schema.org/https://schema.org/postalCode'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/streetAddress'''    
          type: string    
      type: Property    
      x-ngsi:    
        model: https://schema.org/address    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    category:    
      description: 'Restricted traffic area''s category(ies). The purpose of this field is to allow to tag, generally speaking, restricted traffic area entities. Particularities and detailed descriptions should be found under the corresponding specific attributes.'    
      items:    
        enum:    
          - barrierAccess    
          - forBikes    
          - forCustomers    
          - forDisabled    
          - forElectricalVehicles    
          - forEmployees    
          - forMembers    
          - forPedestrian    
          - forVisitors    
          - forResidents    
          - forStudents    
          - gateAccess    
          - guarded    
          - onlyElectricalVehicles    
          - onlyPedestrian    
          - onlyResident    
          - onlyResidents    
          - onlyWithPermit    
          - private    
          - public    
          - publicPrivate    
        type: string    
      minItems: 1    
      type: Property    
      uniqueItems: true    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    description:    
      description: 'A description of this item'    
      type: Property    
    id:    
      anyOf: &restrictedtrafficarea_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Unique identifier of the entity'    
      type: Property    
    location:    
      $id: https://geojson.org/schema/Geometry.json    
      $schema: "http://json-schema.org/draft-07/schema#"    
      oneOf:    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      title: 'GeoJSON Geometry'    
    name:    
      description: 'The name of this item.'    
      type: Property    
    notAllowedVehicleType:    
      description: 'Vehicle type(s) not allowed to cross the restricted traffic area.'    
      items:    
        enum:    
          - anyVehicle    
          - agriculturalVehicle    
          - bicycle    
          - bus    
          - car    
          - caravan    
          - carWithCaravan    
          - carWithTrailer    
          - constructionOrMaintenanceVehicle    
          - dieselCarEuro0    
          - dieselCarEuro1    
          - dieselCarEuro2    
          - dieselCarEuro3    
          - dieselCarEuro4    
          - dieselCarEuro5a    
          - dieselCarEuro5b    
          - dieselCarEuro6    
          - freightTransportVehicle    
          - lorry    
          - moped    
          - motorcycle    
          - motorcycleWithSideCar    
          - motorscooter    
          - petrolCarEuro0    
          - petrolCarEuro1    
          - petrolCarEuro2    
          - petrolCarEuro3    
          - petrolCarEuro4    
          - petrolCarEuro5    
          - petrolCarEuro6    
          - tanker    
          - trailer    
          - van    
        type: string    
      minItems: 1    
      type: Property    
      uniqueItems: true    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *restrictedtrafficarea_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    regulation:    
      description: 'A URL pointing to the regulation for the specific restricted traffic area.'    
      format: uri    
      type: Property    
    restrictionExceptions:    
      description: 'Individual vehicle type allowed to cross the restricted traffic area in a specific time slot.'    
      items:    
        anyOf: *restrictedtrafficarea_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Relationship    
    restrictionValidityHours:    
      description: 'Days of the week and hours in which the traffic restriction is active.'    
      type: Property    
    security:    
      description: 'Security aspects provided by this restricted traffic area.'    
      items:    
        enum:    
          - bollard    
          - camera    
          - cctv    
          - dog    
          - externalSecurity    
          - fencesareaSeperatedFromSurroundings    
          - floodLight    
          - guard24hours    
          - lighting    
          - patrolled    
          - securityStaff    
        type: string    
      minItems: 1    
      type: Property    
      uniqueItems: true    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    specialRestrictions:    
      description: 'Individual vehicle type not allowed to cross the restricted traffic area in a specific time slot.'    
      items:    
        anyOf: *restrictedtrafficarea_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Relationship    
    type:    
      description: 'NGSI Entity type. It has to be RestrictedTrafficArea'    
      enum:    
        - RestrictedTrafficArea    
      type: Property    
    validityEndDate:    
      description: 'The date at which the restriction is dismissed.'    
      format: date-time    
      type: Property    
    validityStartDate:    
      description: 'The date from which the restriction is applied.'    
      format: date-time    
      type: Property    
  required:    
    - id    
    - type    
  type: object    
```  
</details>    
## Ejemplo de carga útil  
#### RestrictedTrafficArea NGSI V2 key-values Ejemplo  
Aquí hay un ejemplo de un RestrictedTrafficArea en formato JSON como key-values. Esto es compatible con NGSI V2 cuando se utiliza `options=keyValues` y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:RestrictedTrafficArea:Milan:RestrictedTrafficAreas:GeoJson:ds51-1",  
  "type": "RestrictedTrafficArea",  
  "category": [  
    "onlyPedestrian"  
  ],  
  "description": "Panel:AP - Stretches:lato civici dispari da piazza Tricolore a via Kramer - Bollards: - Notes:",  
  "location": {  
    "type": "Point",  
    "coordinates": [  
      9.214544,  
      45.483353  
    ]  
  },  
  "name": "Corso Concordia Area",  
  "notAllowedVehicleType": [  
    "anyVehicle"  
  ],  
  "regulation": "Decree:54785/2004, Deliberation:425/2004",  
  "source": "https://dati.comune.milano.it/dataset/ds51_trafficotrasporti_aree_pedonali_ztl_zone_30_",  
  "validityEndDate": "2049-12-31T23:00:00.00Z"  
}  
```  
#### RestrictedTrafficArea NGSI V2 normalizado Ejemplo  
Este es un ejemplo de un RestrictedTrafficArea en formato JSON normalizado. Esto es compatible con NGSI V2 cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:RestrictedTrafficArea:Milan:RestrictedTrafficAreas:GeoJson:ds51-1",  
  "type": "RestrictedTrafficArea",  
  "category": {  
    "type": "array",  
    "value": [  
      "onlyPedestrian"  
    ]  
  },  
  "description": {  
    "type": "string",  
    "value": "Panel:AP - Stretches:lato civici dispari da piazza Tricolore a via Kramer - Bollards: - Notes:"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Point",  
      "coordinates": [  
        9.214544,  
        45.483353  
      ]  
    }  
  },  
  "name": {  
    "type": "string",  
    "value": "Corso Concordia Area"  
  },  
  "notAllowedVehicleType": {  
    "type": "array",  
    "value": [  
      "anyVehicle"  
    ]  
  },  
  "regulation": {  
    "type": "string",  
    "value": "Decree:54785/2004, Deliberation:425/2004"  
  },  
  "source": {  
    "type": "string",  
    "value": "https://dati.comune.milano.it/dataset/ds51_trafficotrasporti_aree_pedonali_ztl_zone_30_"  
  },  
  "validityEndDate": {  
    "type": "DateTime",  
    "value": "2049-12-31T23:00:00.00Z"  
  }  
}  
```  
#### RestrictedTrafficArea NGSI-LD key-values Ejemplo  
Aquí hay un ejemplo de un RestrictedTrafficArea en formato JSON-LD como valores-clave. Esto es compatible con NGSI-LD cuando se utiliza `options=keyValues` y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:RestrictedTrafficArea:Milan:RestrictedTrafficAreas:GeoJson:ds51-1",  
  "type": "RestrictedTrafficArea",  
  "category": [  
    "onlyPedestrian"  
  ],  
  "description": "Panel:AP - Stretches:lato civici dispari da piazza Tricolore a via Kramer - Bollards: - Notes:",  
  "location": {  
    "type": "Point",  
    "coordinates": [  
      9.214544,  
      45.483353  
    ]  
  },  
  "name": "Corso Concordia Area",  
  "notAllowedVehicleType": [  
    "anyVehicle"  
  ],  
  "regulation": "Decree:54785/2004, Deliberation:425/2004",  
  "source": "https://dati.comune.milano.it/dataset/ds51_trafficotrasporti_aree_pedonali_ztl_zone_30_",  
  "validityEndDate": "2049-12-31T23:00:00.00Z",  
  "@context": [  
    "https://schema.lab.fiware.org/ld/context"  
  ]  
}  
```  
#### RestrictedTrafficArea NGSI-LD normalizado Ejemplo  
Este es un ejemplo de un RestrictedTrafficArea en formato JSON-LD normalizado. Esto es compatible con NGSI-LD cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:RestrictedTrafficArea:Milan:RestrictedTrafficAreas:GeoJson:ds51-1",  
  "type": "RestrictedTrafficArea",  
  "category": {  
    "type": "array",  
    "value": [  
      "onlyPedestrian"  
    ]  
  },  
  "description": {  
    "type": "string",  
    "value": "Panel:AP - Stretches:lato civici dispari da piazza Tricolore a via Kramer - Bollards: - Notes:"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Point",  
      "coordinates": [  
        9.214544,  
        45.483353  
      ]  
    }  
  },  
  "name": {  
    "type": "string",  
    "value": "Corso Concordia Area"  
  },  
  "notAllowedVehicleType": {  
    "type": "array",  
    "value": [  
      "anyVehicle"  
    ]  
  },  
  "regulation": {  
    "type": "string",  
    "value": "Decree:54785/2004, Deliberation:425/2004"  
  },  
  "source": {  
    "type": "string",  
    "value": "https://dati.comune.milano.it/dataset/ds51_trafficotrasporti_aree_pedonali_ztl_zone_30_"  
  },  
  "validityEndDate": {  
    "type": "DateTime",  
    "value": "2049-12-31T23:00:00.00Z"  
  },  
  "@context": [  
    "https://schema.lab.fiware.org/ld/context"  
  ]  
}  
```  
