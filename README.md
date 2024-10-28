# Cardapio-Fullstack
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
##### Depois de instalado postgresql , abra o pgAdmin , crie o banco food , e veja qual é o usuario.
##### Vai na pasta src/main/resorces/aplication.properties
###### dentro deste arquivo vai ficar mapeado a `url do banco de dados , o username e a senha`
###### `spring.datasource.url=jdbc:postgresql://localhost:5432/food` `spring.datasource.username=postgres` `spring.datasource.password=password`
##### Para conseguir acessar o Banco de dados e manipular os dados tem

##### a classe de interface `Repository{}` 
###### interface para se comunicar com o banco de dados
###### metodos abstratos crud para manipular e persistir os dados no banco de dados
##### e a classe `Entity`  chamada "Food{}"
###### representa o banco de dados dentro do java
###### vai representar a tabela do banco de dados mapeado para as classes e objetos do java
###### em vez de usar SQL cru , nosso JPA converte Java para SQL.

##### Agora dentro da classe `FoodController{}` e dentro do método `getAll()`
###### crio um objeto do tipo da classe Entity "Food" para apartir dele criar CLasse "Food" em pacote próprio food
###### em cima da assinatura da classe `Food{}` uso mapeamento do jpa para tabela do BD a notação `@Table(name="foods")` e o nome da entity `@Entity(name="foods")` 
###### faça estas duas notações para definir chave primária , e id gerado automaticamente `@Id @GeneratedValue(strategy = GenerationType.IDENTITY)`
###### search for `@GeneratedValue(strategy = GenerationType.UUID)`
###### e agora declare as colunas dentro da classe entity `Food{}`

##### Criar classe `Repository{}` 

###### ela se conecta com o banco de dados e pega os dados
###### tem que ser interface dentro do pacote food que extenda o Objeto JpaRepository<Tipo-Objeto, Tipo-dado-id> `public interface FoodRepository extends JpaRepository<Food, Long> {
}`
###### herda do objeto todos os metodos para manipular dados, usando estes metodos dentro do metodos `getAll()` que fica dentro da classe `FoodController{}`
##### dentro do `FoodController{}`
###### cria um objeto da classe FoodRepository do tipo privado `private FoodRepository repository;`
###### indicar para o Spring que ele faça a injeção dessa dependência dentro da classe `FoodController{}` "que ele se responsabilize para instanciar tal classe quando eu for usar objeto dela"
###### notação para injeção de dependência `@Autowired` bem em cima quando declarei objeto da classe `Food{}` dentro da minha classe `FoodController{}`
##### dentro do `getAll()`
###### cria uma lista do tipo de objeto da classe Food que tem o repository executando seus metodos para trazer tudo do banco de dados `List<Food> foodList = repository.findAll();`
## agora põe para rodar o file main
![image](https://github.com/user-attachments/assets/ade9644f-fff2-46c8-bd5b-94c558342afd)
##### [tutorial](https://youtu.be/QVMPa-DuOgk?si=wRAZe7RiVabRUlVK)

###### Agora vai no insomnia [como usar](https://youtu.be/ww7robHIZbQ?si=4f55d9bkf_sSr0Sm) adiciona uma colection , escolhe o método GET pela url `http://localhost:8080/food` e clica botão [send]
###### vai retornar um array vazio pois n tinha nada no banco ![image](https://github.com/user-attachments/assets/5682f746-0892-4aba-b067-047a9ec60ea0)

##### Não é uma boa pratica retornar do metodo o tipo de dado diretamente a Entity food que fizemos em `getAll()`
###### logo vamos fazer retornar `List<FoodReponseDTO>` na assinatura do método `getAll()`
###### isso vai ser um record "dado estático" que vai receber por parametro os dados igual atributos do objeto Food
###### criar um funil para os objetos tipo Food e um map para cada objeto um data transfer object 
###### `List<FoodResponseDTO> foodlist = repository.findAll().stream().map(FoodResponseDTO::new).toList();`
###### Dentro do record `FoodResponseDTO{}` eu vou receber pelo parametro do contrutor dele um objeto do tipo Food , e por dentro do contrutor vou passando os atributos de um objeto para dentro do record usando os metodos getters gerados pelo lombok dentro do `Food{}`
###### para isso dar certo eu tenho que colocar colado entre assinatura e anotações da classe `Food{}` estas outras anotações que são do lombok `@Getter @NoArgsConstructor @AllArgsConstructor @EqualsAndHashCode(of ="id")`
###### dentro do construtor do record `FoodResponseDTO{}` vai ficar assim 
###### `    public FoodResponseDTO( Food food){  this(food.getId(), food.getTitle(), food.getImage(), food.getPrice() );  }`

## Esta dando erro no food pois ele nap esta criando automaticamente a tabela foods no banco food
![image](https://github.com/user-attachments/assets/f77e0753-ffbc-411a-9e1a-d296bdc1fd3c)
##### vai na config do banco dentro da lateral no intelliJ
![image](https://github.com/user-attachments/assets/fd7f183c-5fe4-4f19-83fb-1a416aab994a)
###### seleciona usuario do banco conectado e senha 
![image](https://github.com/user-attachments/assets/561837ee-1482-4b2d-9910-a7c5e7408eff)
###### clica : aply , ok , ok 



##### Publicar nova comida no cardapio por um metodo dentro do `FoodController{}`
###### `public void saveFood(){}`
###### dentro desta classe marque qual metodo vai fazer mapeamento para requisição POST para esse endpoint food ```    @PostMapping     public void saveFood(){     }```
###### No método de requisição POST o client vai enviar no body o dado que ele quer postar
###### como vamos pegar esse body da requisição através de uma notação do Spring passado como parâmetro `@RequestBody`
###### essa notação avisa o spring para fazer injeção da depêndencia pegando o body do client POST e passar como parâmetro
##### tipo de dado do body que veio do cliente 
###### cria um record FoodRequestTDO
###### ```    
@PostMapping
   public void saveFood(@RequestBody FoodRequestDTO data){

    }```
até aqui 6h20 minuto ainda estou no minuto do video 25:50



## [part2](https://youtu.be/WHruc3_2z68) 
### Desenvolver Front-end e conectar com API 
