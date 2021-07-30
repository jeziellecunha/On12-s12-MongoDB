# Workshop Back end - Reprograma

## 

## Exercício : MongoDB

### Professora: Vanessa Jansen 

### Aluna: Jezielle Cunha

Criar um banco de dados novo (database) e uma coleção com um nome pertinente, de acordo com os dados e tema que você escolher. Os seguintes comandos devem ser feitos e entregues:

- Inserção de documentos:

  ````
  //Criado o database loja_reprograma_fashion, foi gerada a collection produtos que recebeu a inserção abaixo para povoar o banco:

  db.produtos.insertMany([
     {
        "id":1,
        "name":"Jaqueta",
        "description":"Jaqueta de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":499.99
     },
     {
        "id":2,
        "name":"Calça",
        "description":"Calça de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":299.99
     },
     {
        "id":3,
        "name":"Camisa",
        "description":"Camisa de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":199.99
     },
     {
        "id":4,
        "name":"Camiseta",
        "description":"Camiseta de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":99.99
     },
     {
        "id":5,
        "name":"Bermuda",
        "description":"Bermuda de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":199.99
     },
     {
        "id":6,
        "name":"Short",
        "description":"Short de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price":99.99
     },
     {
        "id":7,
        "name":"Blazer",
        "description":"Blazer de alta qualidade fabricado para atender aos clientes mais exigentes",
        "price": 999.99
     }
  ])
  ````

- Buscar todos os produtos:

  ````
  db.getCollection('produtos').find({ })
  ````

- Atualização do preço no produto Jaqueta:

  ````
  db.getCollection('produtos').update(
      {
          "name" : "Jaqueta"
      },
      
      {
          $set:{"price": 299.00}
      }
  );
  ````

- Exclusão de um documento por id:

  ````
  db.getCollection('produtos').remove({
      "id": 5
  })
  ````

- Consulta com projeção- Ordenando do mais caro para o mais barato:

  ````
  db.getCollection('produtos').find({}).sort({price: -1})
  ````

- Consulta utilizando combinação entre os seletores - Buscar produtos que começam com 'Ca' e o preço seja menou ou igual 150.00:

  ````
  db.getCollection('produtos').find({name:/^Ca/, price:{$lte:150.00}})
  ````

- Consulta paginada e ordenada (utilizar *skip*, *limit* e *sort*) - Buscar o terceiro produto de maior preço:

  ````
  db.getCollection('produtos').find({}).sort({price: 1}).skip(2).limit(1)
  ````

  ​