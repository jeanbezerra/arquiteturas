# Estrutura de exemplo

## Diagrama sequencia

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
