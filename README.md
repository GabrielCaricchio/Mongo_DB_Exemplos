# Estudos de mongodb

#### Recomendação de aula para revisão de mongodb:  
https://youtu.be/x9tC0eK0GtA?si=l9z_Oe_v-4WvZNdr

---

#### Servidor mongodb: 
https://www.mongodb.com/try/download/community

<br>

#### Acesso para o terminal para mongodb (precisa do servidor mongodb instalado): 
https://www.mongodb.com/try/download/shell

<br>

#### Interface grafica para mongodb (precisa do servidor mongodb instalado): 
https://www.mongodb.com/products/tools/compass

---

Site 1 com cheat seets: https://quickref.me/mongodb

Site 2 com cheat seets: https://cheatsheets.zip/mongodb

##### Site para treino de mongodb (para quem quiser treinar mongodb sem precisar instalar no computador): 
https://www.mycompiler.io/pt/new/mongodb

---

### Anotações:

Comando antigo para rodar mongodb no terminal: ``` mongo ```


Comando novo para terminal : ``` mongosh ```


• Para criar banco de dados:

``` use pessoasData ```


• Para ver os bancos:

``` show dbs ```


• Obs o banco não é criado até inserir dados nele


• O mongodb não tabelas , tem colletions


• Para criar collections:

``` db.pessoas.insertOne({ nome: "Matheus" , idade: 30, profisssão: "Programador", esta_empregado: true }) ```


• o objectID do mongodb é como se fosse a primary key de um banco relacional

• acknowledged confirma se foi criado


• Para ver as coleções:

``` show collections ```


• Inserção de multiplos dados (1 ou +):

```
db.pessoas.insertMany([
  { nome: "João", idade: 43, profissao: "Arquiteto", esta_empregado: false },
  { nome: "Maria", idade: 23, profissao: "Professora", esta_empregado: true}
])
```


• Para verificação de todos os dados na collection:

``` db.pessoas.find() ```

``` db.pessoas.find().pretty() ```


• Visualização com filtro:

``` db.pessoas.find({ esta_empregado: true }) ```


• Contagem de dados:

``` db.pessoas.find({ esta_empregado: true }).count() ```

``` db.pessoas.find().count() ```


• Retorna apenas um dado:

``` db.pessoas.findOne() ```

``` db.pessoas.findOne({ nome: "Jõao" }) ```


• Atualizar apenas 1:

``` db.pessoas.updateOne({ nome: "João" }, { $set: { esta_empregado: true } }) ```


• matchedCount são a quantidades de dados encontrados que ele alterou

• É possivel acrescentar uma nova chave usando o upate  (ele não serve apenas para alterar valores)

• Atualizar varios dados (1 ou +):

``` db.pessoas.updateMany({}, {$set: { salario: 5000 })```


• Para remover 1 dado:

``` db.pessoas.deleteOne({ nome: "Matheus" }) ```


• deletedCount indica a quantidade de dados deletados

• Para deletar varios dados (1 ou +):

``` db.pessoas.deleteMany({ name: "Josias"}) ```


• Operadores:
- Maior que algo:

``` db.pesssoas.find( { idade { $gt: 30 } }) ```

- Maior ou igual:

``` db.pesssoas.find( { idade { $gte: 30 } }) ```

- Menor que:

``` db.pesssoas.find( { idade { $lt: 30 } }) ```

- Menor ou igual a:

``` db.pesssoas.find( { idade { $lte: 30 } }) ```


• Usando operadores para fazer update especifico:

``` db.pessoas.updateMany({ idate: { $gt: 35}, { $set: {prioridade: True}) ```

• Tipos de dados disponiveis:
```
db.pessoas.insertOne({
  nome: "Paula",
  idade: 44,
  hobbies: ["Correr", "Ler", "Trilhas"],
  esta_trabalhando: true,
  data_cadastro: new Date(),
  caracteristicas: {
    cor_dos_olhos: "azuis",
    altura: 1.82,
    perfil: "Extrovertida"
  }
})
```

- string, number, array,booleano, data, document, number(float) 
- Para variar tipos de dados geralmente o document é a melhor opção, quando queremos uma lista de um tipo de dado unico geralmente o array é melhor opção 


• Operadores exclusivos do update:
- Incremento (inc, serve para valores positivos e negativos):
  
``` db.pessoas.updateOne({ nome: "Maria" }, { $inc: { salario: 1000 } } ```


• Criar Indice:

``` db.pessoas.createIndex({ "nome" }) ```


• Como atestar que tem o indice realmente criado:

``` db.pessoas.detIndexes() ```


• Como saber se o mongodb está usando o indice:

``` db.pessoas.explain().find({ nome: "João" }) ```


• Como remover indice:

``` db.pessoas.dropIndex("nome_1") ```


• Deletar collection:

``` db.pessoas.drop() ```


• Para deletar o banco:

``` db.dropDatabase() ```

