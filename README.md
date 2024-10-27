# Card-pio-Fullstack
Version 1.0
## [part1](https://youtu.be/lUVureR5GqI?si=MrS2uFq2hSk-41yY)
### Desenvolver API usando Java Spring + bd Postgres

#### Ir no spring initializer [link aqui](https://start.spring.io/) para acelerar processo de desenvolvimento configurando as dependências.
##### maven, java, spring boot 3.4.0, java17, name : cardapio-fullstack, artifact : cardapio-fullstack, description: cardapio digital
##### add dependencies : spring boot dev tools"reload automático", spring web"pra criar aplicações web", lombok"gera métodos automáticos do java in runtime"
##### dentro do intellij na barra lateral
###### clicar para instalar as dependências : maven, seu-projeto, lifecycle, package
##### os files de dependencia fica dentro do arquivo pom.xml

##### configuração inicial do intellij
###### com file main selecionado vai nas configurações e clica : build execution deployment, compiler, ativar `[]build project automaticaly`
###### clica em aply
###### mesmo menu , vai em:  advanced settings, clicar no check compiler `[]Allow auto-make to start even if developed aplication is currently running`
###### marca o ok e pronto

##### Criar arquivo `FoodController.java`
###### responsável por concentrar os requests para pegar os dados do cardápio e armazenar mais info no banco de dados
###### package adicionar `package com.example.cardapio_fullstack.controller;`
###### fazer notação spring da classe ser o controler `@RestController bem emcima da linha que tem assinatura do método`
###### definir endpoint `@RequestMapping("food")`

##### Requisições do front-end 
###### cria um método dentro da classe para retornar para o front-end todos cardápios do bando ` public tipo getAll(){}`
###### definir como o método vai ser chamado `@GetMapping public tipo getAll(){}`
###### quando bater no endpoint "food" o Get é para chamar este método `getAll`

##### Conectar com Banco de Dados, pegar as informações la dentro e retornar neste endpoint
###### vai no spring initializer [link aqui](https://start.spring.io/) e baixa mais dependências
###### seleciona para maven
###### dependências : spring data JPA"persistências de dados sql para java", PostgreSQL driver"conectar aplicação com Banco de dados"
###### clica em explore , dentro do pom.xml online seleciona as tags que tem JPA  e POSTEGRESQL copiar para colar dentro das dependências do projeto no intellij
###### aperta no reload para atualizar no intellij
![image](https://github.com/user-attachments/assets/b2393718-8a5a-4d68-9ce3-04138f961a09)
##### Vai na pasta src/main/resorces/aplication.properties
###### dentro deste arquivo vai ficar mapeado a `url do banco de dados , o username e a senha`
###### `spring.datasource.url=jdbc:postgresql://localhost:5432/food` `spring.datasource.username=thiagodesenvolvedor` `spring.datasource.password=password`
##### Para conseguir acessar o Banco de dados e manipular os dados

##### criar a classe de interface `Repository{}` 
###### interface para se comunicar com o banco de dados
###### metodos abstratos crud para manipular e persistir os dados no banco de dados
##### e classe `Entity`  chamada "Food{}"
###### representa o banco de dados dentro do java
###### vai representar a tabela do banco de dados mapeado para as classes e objetos do java
###### em vez de usar SQL cru , nosso JPA converte Java para SQL.

##### Agora dentro da classe `FoodController{}` e dentro do método `getAll()`
###### crio um objeto do tipo da classe Entity "Food" para apartir dele criar CLasse "Food" em pacote próprio food
###### em cima da assinatura da classe `Food{}` uso mapeamento do jpa para tabela do BD a notação `@Table(name="foods")` e o nome da entity `@Entity(name="foods")` 
###### faça estas duas notações para definir chave primária , e id gerado automaticamente `@Id @GeneratedValue(strategy = GenerationType.IDENTITY)`
###### search for `@GeneratedValue(strategy = GenerationType.UUID)`
###### e agora declare as colunas dentro da classe entity `Food{}`

até aqui 2h12 minuto ainda estou no minuto do video 1 17


## [part2](https://youtu.be/WHruc3_2z68) 
### Desenvolver Front-end e conectar com API 
