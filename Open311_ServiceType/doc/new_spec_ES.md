Entidad: Open311_ServiceType  
============================







```yaml  
Open311_ServiceType:    
  description: 'As per Open311 an entity of type ServiceType is an acceptable 311 service request type. A request type can be unique to the city/jurisdiction.'    
  properties:    
    address:    
      description: 'The mailing address.'    
      properties:    
        addressCountry:    
          type: string    
        addressLocality:    
          type: string    
        addressRegion:    
          type: string    
        areaServed:    
          type: string    
        postOfficeBoxNumber:    
          type: string    
        postalCode:    
          type: string    
        streetAddress:    
          type: string    
      type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided.'    
      type: Property    
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
      anyOf: &open311_servicetype_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
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
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *open311_servicetype_-_properties_-_owner_-_items_-_anyof    
      type: Property    
    seeAlso:    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity type'    
      enum:    
        - Open311ServiceType    
      type: string    
  required:    
    - id    
    - type    
  type: object    
```  



  "id": "o311:servicetype-guadalajara-sidewalks",  
  "type": "Open311ServiceType",  
  "dateCreated": "2007-01-01T12:00:00Z",  
  "jurisdiction_id": "www.smartguadalajara.com",  
  "open311:type": "realtime",  
  "service_code": 234,  
  "service_name": "Aceras",  
  "description": "When a sidewalk is broken or dirty allows citizens to request a fix",  
  "keywords": "street,sidewalk, cleaning, repair",  
  "group": "street",  
  "attributes": [  
    {  
      "variable": true,  
      "code": "ISSUE_TYPE",  
      "datatype": "singlevaluelist",  
      "required": true,  
      "datatype_description": "",  
      "order": 1,  
      "description": "What is the identified problem at the sidewalk?",  
      "values": [  
        {  
          "key": 123,  
          "name": "Bump"  
        },  
        {  
          "key": 124,  
          "name": "Dirty"  
        }  
      ]  
    }  
  ]  
}  
```  



  "id": "o311:servicetype-guadalajara-sidewalks",  
  "type": "Open311ServiceType",  
  "group": {  
    "value": "street"  
  },  
  "description": {  
    "value": "When a sidewalk is broken or dirty allows citizens to request a fix"  
  },  
  "service_code": {  
    "value": 234  
  },  
  "service_name": {  
    "value": "Aceras"  
  },  
  "open311:type": {  
    "value": "realtime"  
  },  
  "jurisdiction_id": {  
    "value": "www.smartguadalajara.com"  
  },  
  "dateCreated": {  
    "type": "DateTime",  
    "value": "2007-01-01T12:00:00Z"  
  },  
  "keywords": {  
    "value": "street,sidewalk, cleaning, repair"  
  },  
  "attributes": {  
    "value": [  
      {  
        "code": "ISSUE_TYPE",  
        "description": "What is the identified problem at the sidewalk?",  
        "datatype": "singlevaluelist",  
        "required": true,  
        "values": [  
          {  
            "name": "Bump",  
            "key": 123  
          },  
          {  
            "name": "Dirty",  
            "key": 124  
          }  
        ],  
        "variable": true,  
        "order": 1,  
        "datatype_description": ""  
      }  
    ]  
  }  
}  
```  



              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "attributes": [{"code": "ISSUE_TYPE",  
                 "datatype": "singlevaluelist",  
                 "datatype_description": "",  
                 "description": "What is the identified problem at the "  
                                "sidewalk?",  
                 "order": 1,  
                 "required": True,  
                 "values": [{"key": 123, "name": "Bump"},  
                            {"key": 124, "name": "Dirty"}],  
                 "variable": True}],  
 "createdAt": "2007-01-01T12:00:00Z",  
 "description": "When a sidewalk is broken or dirty allows citizens to request "  
                "a fix",  
 "group": "street",  
 "id": "urn:ngsi-ld:Open311ServiceType:o311:servicetype-guadalajara-sidewalks",  
 "jurisdiction_id": "www.smartguadalajara.com",  
 "keywords": "street,sidewalk, cleaning, repair",  
 "open311:type": "realtime",  
 "service_code": 234,  
 "service_name": "Aceras",  
 "type": "Open311ServiceType"}  
```  



    "id": "urn:ngsi-ld:Open311ServiceType:o311:servicetype-guadalajara-sidewalks",  
    "type": "Open311ServiceType",  
    "createdAt": "2007-01-01T12:00:00Z",  
    "group": {  
        "type": "Property",  
        "value": "street"  
    },  
    "description": {  
        "type": "Property",  
        "value": "When a sidewalk is broken or dirty allows citizens to request a fix"  
    },  
    "service_code": {  
        "type": "Property",  
        "value": 234  
    },  
    "service_name": {  
        "type": "Property",  
        "value": "Aceras"  
    },  
    "open311:type": {  
        "type": "Property",  
        "value": "realtime"  
    },  
    "jurisdiction_id": {  
        "type": "Property",  
        "value": "www.smartguadalajara.com"  
    },  
    "keywords": {  
        "type": "Property",  
        "value": "street,sidewalk, cleaning, repair"  
    },  
    "attributes": {  
        "type": "Property",  
        "value": [  
            {  
                "code": "ISSUE_TYPE",  
                "description": "What is the identified problem at the sidewalk?",  
                "datatype": "singlevaluelist",  
                "required": true,  
                "values": [  
                    {  
                        "name": "Bump",  
                        "key": 123  
                    },  
                    {  
                        "name": "Dirty",  
                        "key": 124  
                    }  
                ],  
                "variable": true,  
                "order": 1,  
                "datatype_description": ""  
            }  
        ]  
    },  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context",  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
    ]  
}  
```  