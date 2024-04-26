# Diagrama sequencia

## Exemplo 1

```sh
@startuml
!theme materia-outline
actor User
User -> Sales: ProcessOrder
  activate Sales #FFBBBB
  Sales -> Warehouse: << packOrder >>
    activate Warehouse #gold
    Warehouse -> Picker: GetProducts
      activate Picker #005500
      Picker --> Warehouse: ProductsCollected
      deactivate Picker
    Warehouse --> Sales: OrderPacked
    deactivate Warehouse
  Sales -> Sales: SendOrder
  Sales -> User: OrderSent
  deactivate Sales
@enduml
```

![alt text](plantuml-diagrams/img/diagram-sequence.svg "sequence-1")
