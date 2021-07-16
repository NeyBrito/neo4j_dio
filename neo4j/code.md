# Introdução ao MongoDB e Bancos de Dados NoSQL

### Bootcamp Data Engineer Banco Carrefour



#### Tipos de Bancos de Dados NoSQL

##### Ferramenta Utilizada

- sandbox.neo4j.com

##### Neo4j

- Criação de nó (dados)
  - CREATE (:Cliente {name:"Bob Esponja", age: 26, hobbies: ['Caça agua-viva, Comer hamburgueres']}) 

- Consulta do nó
  - MATCH (bob_esponja) RETURN bob_esponja
- Relação entre nós 
  - CREATE (:Cliente {name: "Lula Molusco", age: 30, hobbies: ['Tocar clarinete']}) - [:Bloqueado]->(:Cliente {name: "Patrick", hobbies:['caçar Agua-Viva']})
- Validação de Item
  - CREATE(:Object)
- Relacionamento entre dois nós existentes
  - MATCH (lula:Cliente {name:"Lula Molusco"}), (patrick:Cliente{name:"Patrick"}) CREATE (lula)-[:Bloqueado]->(patrick)

- Remover um relacionamento 
  - MATCH (bob:Cliente {name: "Bob Esponja"})-[relaciona:Bloqueado]-() DELETE relaciona
- Criação de Relacionameto AMIGO
  - MATCH (bob:Cliente {name: "Bob Esponja"}), (patrick:Cliente{name: "Patrick"}) CREATE(bob)-[:Amigo]->(patrick)
- Excluindo um nó
  - MATCH (lula:Cliente {name: "Lula Molusco"}) DELETE lula
- Atualizando dados 
  - MATCH (patrick:Cliente{name:"Patrick"}) SET patrick.age = [38]
- Alterando lable
  - MATCH (patrick:Cliente {name: "Patrick"}) SET patrick:Cliente_Premium