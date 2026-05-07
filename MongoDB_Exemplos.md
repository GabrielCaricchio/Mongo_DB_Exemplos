

# 1. Ver bancos de dados

show dbs

Mostra todos os bancos existentes.

# 2. Criar ou usar banco

use escola

Cria (ou acessa) o banco chamado escola.

# 3. Ver coleções

show collections

Mostra as coleções do banco atual.

# 4. Criar coleção

db.createCollection("alunos")


Cria a coleção alunos.

# 5. Inserir um documento

db.alunos.insertOne({
  nome: "Carlos",
  idade: 20,
  curso: "ADS"
})

Insere 1 documento.

# 6. Inserir vários documentos

db.alunos.insertMany([
  {
    nome: "Ana",
    idade: 21,
    curso: "SI"
  },
  {
    nome: "Pedro",
    idade: 19,
    curso: "ADS"
  }
])

Insere vários registros.

# 7. Buscar todos os documentos

db.alunos.find()

Lista todos os alunos.

# 8. Buscar com formatação bonita

db.alunos.find().pretty()

Organiza melhor a visualização.

# 9. Buscar um documento

db.alunos.findOne()

Retorna apenas 1 documento.

# 10. Buscar por campo

db.alunos.find({
  nome: "Carlos"
})

Busca aluno pelo nome.

# 11. Buscar usando operadores

## Maior que

db.alunos.find({
  idade: { $gt: 18 }
})

## Menor que

db.alunos.find({
  idade: { $lt: 21 }
})

## Maior ou igual

db.alunos.find({
  idade: { $gte: 20 }
})


## Menor ou igual


db.alunos.find({
  idade: { $lte: 20 }
})


# 12. Atualizar um documento


db.alunos.updateOne(
  { nome: "Carlos" },
  {
    $set: {
      idade: 25
    }
  }
)


Atualiza apenas 1 documento.

# 13. Atualizar vários documentos


db.alunos.updateMany(
  {},
  {
    $set: {
      ativo: true
    }
  }
)


Adiciona o campo ativo para todos.

# 14. Incrementar valor


db.alunos.updateOne(
  { nome: "Ana" },
  {
    $inc: {
      idade: 1
    }
  }
)


Soma +1 na idade.

# 15. Deletar um documento


db.alunos.deleteOne({
  nome: "Pedro"
})


Remove 1 documento.

# 16. Deletar vários documentos


db.alunos.deleteMany({
  curso: "ADS"
})


Remove vários documentos.

# 17. Ordenar resultados

## Crescente


db.alunos.find().sort({
  idade: 1
})


## Decrescente


db.alunos.find().sort({
  idade: -1
})


# 18. Limitar resultados


db.alunos.find().limit(2)


Mostra apenas 2 documentos.

# 19. Contar documentos


db.alunos.countDocuments()


Conta quantos documentos existem.

# 20. Buscar campos específicos


db.alunos.find(
  {},
  {
    nome: 1,
    curso: 1
  }
)


Mostra apenas nome e curso.

# 21. Documento com array


db.alunos.insertOne({
  nome: "Lucas",
  telefones: [
    "99999-9999",
    "88888-8888"
  ]
})


Exemplo de lista dentro do documento.

# 22. Documento embutido


db.alunos.insertOne({
  nome: "Marina",
  endereco: {
    rua: "Rua A",
    numero: 100
  }
})


Exemplo de objeto dentro do documento.

# 23. Buscar em array


db.alunos.find({
  telefones: "99999-9999"
})


# 24. Apagar coleção


db.alunos.drop()


Remove a coleção inteira.

# 25. Apagar banco de dados


db.dropDatabase()


Remove o banco atual.

# Mini exercício para os alunos


// 1. Criar banco escola
// 2. Criar coleção alunos
// 3. Inserir 5 alunos
// 4. Buscar todos
// 5. Atualizar um aluno
// 6. Deletar um aluno
// 7. Ordenar por idade


# Dica importante para os alunos

MongoDB trabalha com documentos JSON/BSON.
Cada registro possui:


{
  campo: valor
}


Exemplo:


{
  nome: "Carlos",
  idade: 20
}
