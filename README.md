# metaobj
Metaobj creates, validates, and initializes objects at runtime. A domain model can now be defined more easily than ever before in an ubiquitous language such as YAML or JSON. Under the hood, metaobj uses object metadata defined in a configuration file such as YAML to create, validate, and intialize an object at runtime.


## How Object Metadata looks?
```
---
metaobj:
  object_name:
    required: true
  # element_id is autogenerated
  element_id:
    required: false
  element_name:
    required: true
  element_description:
    required: false
  element_type:
    required: true
    enum:
      - integer
      - float
      - character
      - string
      - boolean
      - tuple
      - array
  element_length:
    required: true
  element_privileges:
    required: false
    enum:
      - public
      - private
    default: public
  element_created_by:
    required: false
    default: "metaobj"
  element_created_on:
    required: false  
  element_modified_by:
    required: false
    default: "metaobj"  
  element_modified_on:
    required: false  
```


## How users define a domain object?
```
---
employee:
  employee_name:
    type: string
    description: "Employee's name"
    length: 50
    privileges: public
    created_by: "User1"
```
