# <h1>Cardapio-Fullstack</h1>
###### [próxima aplicação para eu fazer tudo usando docker](https://medium.com/swlh/creating-and-deploying-a-full-stack-web-application-31ad5c9f3b77#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImM4OGQ4MDlmNGRiOTQzZGY1M2RhN2FjY2ZkNDc3NjRkMDViYTM5MWYiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJhenAiOiIyMTYyOTYwMzU4MzQtazFrNnFlMDYwczJ0cDJhMmphbTRsamRjbXMwMHN0dGcuYXBwcy5nb29nbGV1c2VyY29udGVudC5jb20iLCJhdWQiOiIyMTYyOTYwMzU4MzQtazFrNnFlMDYwczJ0cDJhMmphbTRsamRjbXMwMHN0dGcuYXBwcy5nb29nbGV1c2VyY29udGVudC5jb20iLCJzdWIiOiIxMDU5ODMxODQzOTU2NjA3NDQ5OTciLCJlbWFpbCI6InRoaWFnb21hc3Nlbm8zQGdtYWlsLmNvbSIsImVtYWlsX3ZlcmlmaWVkIjp0cnVlLCJuYmYiOjE3MzAxNDg5NTIsIm5hbWUiOiJUaGlhZ28gTWFzc2VubyIsInBpY3R1cmUiOiJodHRwczovL2xoMy5nb29nbGV1c2VyY29udGVudC5jb20vYS9BQ2c4b2NKSWpSYzNPQW5fZE96M0VGaEtqc0xYc1ItMVZ2S2s1TzhiQ21QU3ZFMng1c1EtWFM4PXM5Ni1jIiwiZ2l2ZW5fbmFtZSI6IlRoaWFnbyIsImZhbWlseV9uYW1lIjoiTWFzc2VubyIsImlhdCI6MTczMDE0OTI1MiwiZXhwIjoxNzMwMTUyODUyLCJqdGkiOiI0MDNmZTM1ZDEyN2I5NTU4ZDM4NTk3Y2ZkN2YwZmI0ZTIyYzE5MTQ4In0.F74XE-jYab5j7q8nl0K2146j53L8nTnb_ywoPSapCXeITRuegZ3yitkUJqbKJqObDs3ODyejrp1-VeEyE6nqAg8ofSKvsbZnru947dNKsQv4WJLd1IwLA3-WixbCoa0nctoHDBkFvQGNfk0NVoZFMhvC6kSNzCTZXNnxWDOgBCtwBq9DSVCAIEDIjl2CRTHUBwrlNmhnqjvzYleROB4copcMw6raw_RzIwXy1RzIaXfEYFxA7YZA9MhYJoSsMkPL_K5Tg0u_A2y-MlrUVTMLb05aljCNedJt__LtWXza27BNWVjGatqBePuH6h7x1FO_6obFo61E3w7FDD4qfeNOdA:~:text=%F0%9F%8E%89%F0%9F%8E%89%F0%9F%8E%89%20Congratulations!%20We%E2%80%99ve%20now,Production%20Deploy)
Version 1.0
# Tecnologias
## Front-end:
##### TypeScript
##### React
##### React - Bibliotecas - `react query` , `axios`
## Back-end 
##### java
##### spring initializer
##### PostgreSQL


## [part1](https://youtu.be/lUVureR5GqI?si=MrS2uFq2hSk-41yY)
### Desenvolver API usando Java Spring + bd Postgres
##### - Criar rotas , 
##### - Fazer conexão com banco de dados, 
##### - Fazer as entidades do banco de dados e repositorio
#### --------------------------------------------------------------------------------------------------------------------------------
### Ir no spring initializer [link aqui](https://start.spring.io/) para acelerar processo de desenvolvimento configurando as dependências.
##### maven, 
##### java, 
##### spring boot 3.4.0, 
##### java17, 
##### name : cardapio-fullstack, 
##### artifact : cardapio-fullstack, 
##### description: cardapio digital
### Adicionar dependências ao spring boot : 
##### spring boot dev tools"reload automático", 
##### spring web"pra criar aplicações web", 
##### lombok"gera métodos automáticos do java in runtime"
##### --------------------------------------------------------------------------------------------------------------------------------
### Dentro do intellij na barra lateral
###### clicar nos botões com estes nomes para instalar as dependências dentro da IDE : maven, seu-projeto, lifecycle, package
##### os files de dependencia fica dentro do arquivo pom.xml
#### ---------------------------------------------------------------------------------------------------------------------------------
### Configuração inicial do intellij
###### com file main selecionado vai nas configurações e clica : build execution deployment, compiler, ativar `[]build project automaticaly`
###### clica em aply
###### mesmo menu , vai em:  advanced settings, clicar no check compiler `[]Allow auto-make to start even if developed aplication is currently running`
###### marca o ok e pronto
#### ---------------------------------------------------------------------------------------------------------------------------------
### Criar arquivo `FoodController.java`
###### responsável por concentrar os requests para pegar os dados do cardápio e armazenar mais info no banco de dados
###### package adicionar `package com.example.cardapio_fullstack.controller;`
###### fazer notação spring da classe ser o controler `@RestController bem emcima da linha que tem assinatura do método`
###### definir endpoint `@RequestMapping("food")`
#### ---------------------------------------------------------------------------------------------------------------------------------
### Requisições do front-end 
###### cria um método dentro da classe para retornar para o front-end todos cardápios do banco de dados ` public tipo getAll(){}`
###### definir como o método vai ser chamado `@GetMapping public tipo getAll(){}`
###### quando bater no endpoint "food" o Get é para chamar este método `getAll`
#### ---------------------------------------------------------------------------------------------------------------------------------
### Conectar com Banco de Dados, pegar as informações la dentro e retornar neste endpoint
###### vai no spring initializer [link aqui](https://start.spring.io/) e baixa mais dependências
###### seleciona para maven
###### dependências : 
###### spring data JPA"persistências de dados sql para java", 
###### PostgreSQL driver"conectar aplicação com Banco de dados"
###### clica em explore , dentro do pom.xml online seleciona as tags que tem JPA  e POSTEGRESQL copiar para colar dentro das dependências do projeto no intellij
###### aperta no reload para atualizar no intellij
![image](https://github.com/user-attachments/assets/b2393718-8a5a-4d68-9ce3-04138f961a09)
#### ---------------------------------------------------------------------------------------------------------------------------------
### Depois de instalado postgresql , abra o pgAdmin , crie o banco food , e veja qual é o usuario.
###### Precisa: ligar o pgAdmin, entrar com senha bd, conectar usuario e senha do banco do IntelliJ, executar backend no intelliJ , aí vejo se no navegador aparece igual a kipper dev
##### Vai na pasta src/main/resorces/aplication.properties
###### dentro deste arquivo vai ficar mapeado a `url do banco de dados , o username e a senha`
###### `spring.datasource.url=jdbc:postgresql://localhost:5432/food` 
###### `spring.datasource.username=postgres` 
###### `spring.datasource.password=password`
###### Primeiro criar o banco e deixar ele rodando antes de conseguir acessar e ou manipular os dados dele
#### ---------------------------------------------------------------------------------------------------------------------------------
### A classe de interface `Repository{}` 
###### interface para se comunicar com o banco de dados
###### metodos abstratos crud para manipular e persistir os dados no banco de dados
### E a classe `Entity`  chamada "Food{}"
###### representa o banco de dados dentro do java
###### vai representar a tabela do banco de dados mapeado para as classes e objetos do java
###### em vez de usar SQL cru , nosso JPA converte Java para SQL.
#### ---------------------------------------------------------------------------------------------------------------------------------
### Agora dentro da classe `FoodController{}` e dentro do método `getAll()`
###### crio um objeto do tipo da classe Entity "Food" para apartir dele criar CLasse "Food" em pacote próprio food
###### em cima da assinatura da classe `Food{}` uso mapeamento do jpa para tabela do BD a notação `@Table(name="foods")` e o nome da entity `@Entity(name="foods")` 
###### faça estas duas notações para definir chave primária , e id gerado automaticamente `@Id @GeneratedValue(strategy = GenerationType.IDENTITY)`
###### search for `@GeneratedValue(strategy = GenerationType.UUID)`
###### e agora declare as colunas dentro da classe entity `Food{}`
#### ---------------------------------------------------------------------------------------------------------------------------------
### Criar classe `Repository{}` 
###### ela se conecta com o banco de dados e pega os dados
###### tem que ser interface dentro do pacote food que extenda o Objeto `JpaRepository<Tipo-Objeto, Tipo-dado-id>`
```
public interface FoodRepository extends JpaRepository<Food, Long> {
}
```
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
#### ---------------------------------------------------------------------------------------------------------------------------------
### Agora vai no insomnia [como usar](https://youtu.be/ww7robHIZbQ?si=4f55d9bkf_sSr0Sm) adiciona uma colection , escolhe o método GET pela url `http://localhost:8080/food` e clica botão [send]
###### vai retornar um array vazio pois n tinha nada no banco ![image](https://github.com/user-attachments/assets/5682f746-0892-4aba-b067-047a9ec60ea0)

##### Não é uma boa pratica retornar do metodo o tipo de dado diretamente a Entity food que fizemos em `getAll()`
###### logo vamos fazer retornar `List<FoodReponseDTO>` na assinatura do método `getAll()`
###### isso vai ser um record "dado estático" que vai receber por parametro os dados igual atributos do objeto Food
###### criar um funil para os objetos tipo Food e um map para cada objeto um data transfer object 
###### `List<FoodResponseDTO> foodlist = repository.findAll().stream().map(FoodResponseDTO::new).toList();`
###### Dentro do record `FoodResponseDTO{}` eu vou receber pelo parametro do contrutor dele um objeto do tipo Food , e por dentro do contrutor vou passando os atributos de um objeto para dentro do record usando os metodos getters gerados pelo lombok dentro do `Food{}`
###### para isso dar certo eu tenho que colocar colado entre assinatura e anotações da classe `Food{}` estas outras anotações que são do lombok 
###### @Getter 
###### @NoArgsConstructor 
###### @AllArgsConstructor 
###### @EqualsAndHashCode(of ="id")`
###### dentro do construtor do record `FoodResponseDTO{}` vai ficar assim 
```    
public FoodResponseDTO( Food food){
      this( food.getId(), food.getTitle(), food.getImage(), food.getPrice() );
}
```
#### ---------------------------------------------------------------------------------------------------------------------------------
### Esta dando erro no food pois ele nap esta criando automaticamente a tabela foods no banco food
![image](https://github.com/user-attachments/assets/f77e0753-ffbc-411a-9e1a-d296bdc1fd3c)
##### vai na config do banco dentro da lateral no intelliJ
![image](https://github.com/user-attachments/assets/fd7f183c-5fe4-4f19-83fb-1a416aab994a)
###### seleciona usuario do banco conectado e senha 
![image](https://github.com/user-attachments/assets/561837ee-1482-4b2d-9910-a7c5e7408eff)
###### clica : aply , ok , ok 
#### ---------------------------------------------------------------------------------------------------------------------------------
### Publicar nova comida no cardapio por um metodo dentro do `FoodController{}`
###### `public void saveFood(){}`
###### dentro desta classe marque qual metodo vai fazer mapeamento para requisição POST para esse endpoint food 
```    
@PostMapping public void saveFood(){
	//resto do código
}
```
###### No método de requisição POST o client vai enviar no body o dado que ele quer postar
###### como vamos pegar esse body da requisição através de uma notação do Spring passado como parâmetro `@RequestBody`
###### essa notação avisa o spring para fazer injeção da depêndencia pegando o body do client POST e passar como parâmetro
##### tipa o dado do body que veio do cliente 
###### cria um record FoodRequestTDO
```
@PostMapping
public void saveFood(@RequestBody FoodRequestDTO data){
}
```
###### definindo os parametros do record n precisa do id pois isso é responsabilidade do servidor gerar id automático e não do record
```
package com.example.cardapio_fullstack.food;
public record FoodRequestDTO( String title, String image, Integer price) {   
}
```
###### usar o objeto `repository`que manipula os dados no banco , para receber por parâmetro o body do client e salvar na tupla do bd
```
repository.save(data);
```
###### o repository espera salvar tipo dado Entity Food e não record, logo preciso converter DTO --> Food
###### repository recebe por um construtor especial tipo dato DTO ```Food foodData = new Food(data);```
###### na classe `Food{}` devo criar construtor que passa os valores do tipo DTO para os atributos da classe
```
    public Food(FoodRequestDTO data) {
        this.image = data.image();
        this.title = data.title();
        this.price = data.price();
    }
```
###### e da um return fazio do tipo void dentro do método `saveFood()`
```
    @PostMapping
    public void saveFood(@RequestBody FoodRequestDTO data){
        Food foodData = new Food(data);
        repository.save(foodData);
        return;
    }
```
##### Agora vai disparar uma requisição do tipo POST para o endpoint `/food` dentro do insomnia
###### crie um novo request , tipo POST para a url 
```
http://localhost:8080/food
```
###### dentro do body , escolha formato json e coloque dentro do file body-content 
```
{
	"price": 24,
	"title": "hamburguer",
	"image": "https://moinhoglobo.com.br/wp-content/uploads/2019/05/16-hamburguer.jpeg"
}
```
###### e para enviar requisição click : send 
###### se retornar 200 ok , faça um get para mesma url para verificar se realmente foi adicionada no banco ou não
![image](https://github.com/user-attachments/assets/916ab487-b929-4316-a297-d0989af41f23)
![image](https://github.com/user-attachments/assets/cf351c5d-4a43-4e0f-87e6-a3e10fd3f5fc)
##### O tipo de ID  gerado pelo servidor do tipo = print abaixo, não é válido para sistemas que vão para produção (um software de uma empresa) 
![image](https://github.com/user-attachments/assets/1852ca72-dc02-4d85-b964-0faf28a06650)
##### pois ter definido a notação JPA para gerar sequencialmente os ID, não é seguro para o sistema privado.
##### Mais seguro usar tipo UUID para ninguém conseguir adivinhar o id de algum objeto que esta armazenado no banco, ou seja, chutar o id de algum dado e conseguir capturar essa informação privada de uma maneira pública não permitida.
##### E por último a configuração do Course dentro do controller
### ... voltando ao assundo do código para esta aplicação web :
##### em cada metodo colocar perto de assinatura dele 
```
@CrossOrigin(origins = "*",allowedHeaders = "*")
```
###### origins = "*" , para permitir de todas as origins
###### pode restringuir para dominio apenas da aplicação origins = "dominio-aplicacao" quando for fazer o deploy.
```
exemplo a minha aplicação esta rodando no meu localhost na porta 3000
```
###### `origins="http://localhost:3000"`
###### allowedHeaders = "*" , para permitir todos os headers que vierem do meu cliente

até aqui 8h30 

## [part2](https://youtu.be/WHruc3_2z68) 
### Desenvolver Front-end e conectar com API 
#### ---------------------------------------------------------------------------------------------------------------------------------
### Consumir e publicar dados
##### Criar um componente que recebe como parametro um objeto que implemente uma interface para traduzir o que vier FoodRequestBody para dentro do componente card
##### receber dados da api para dentro da array data dentro do componente app
###### ```data.map(foodData => <Card/>``` para cada um objeto dentro da array data retorne um componente Card
##### Criar uma nova interface para receber o objeto que vier da api
##### para pegar os dados do backeend estando no frontend precisamos usar a lib [react query](https://www.npmjs.com/package/react-query) [tutorial1](https://youtu.be/4n6cD9M21-s?si=kppGT0tQF7zk_Z3G) [tutorial2](https://youtu.be/8K1N3fE-cDs?si=qldbrA4Gi1p9YlgN) [tutorial kipper](https://youtu.be/ZI9uLACYAd0?si=7QkHngn7esT35xze)
```
	npm install tanstack-query/react-query
```
####### se n funcionar testar este 
```
npm i @tanstack/react-query
```
###### declare este hook baixado dentro de uma pasta ./hooks/useFoodData.ts , 
###### o file `useFoodData.ts` vai ser usado para fazer o fetch nos dados e salvar em uma variavel para conseguir usar
###### usar lib axios para disparar requisição HTTP
```
npm install axios
```
###### usar lib axios dentro do componente `useFoodData.ts` 
###### chame o metodo `useFoodData` dentro do componente `App.tsx`
``` data: query.data?.data  ``` tem tudo isso explicado no video [kipper](https://youtu.be/n8RLfLunQzc?si=X7Ta1jBoPZ-umiKP)
##### Agora execute a aplicação para test 

´´´
npm run dev
´´´

###### Precisa: ligar o pgAdmin, entrar com senha bd, conectar usuario e senha do banco do IntelliJ, executar backend no intelliJ , aí vejo se no navegador aparece igual a kipper dev
![image](https://github.com/user-attachments/assets/a764d9f2-160b-4e27-9cb4-fedeba423c75)
##### Erro induzido
###### Fornercer um QueryClientPRovider empacotando componente principal da aplicação e passando um client pelo props
##### Fazer o enfeito da parte front-end dentro do components/card/card.tsx ``
###### use o insomnia para colocar mais pratos no cardápio
![image](https://github.com/user-attachments/assets/80a8c508-69c3-4bc7-a574-14aefe7dcba9)
![image](https://github.com/user-attachments/assets/04d6b4e4-831a-4328-a0a5-75a9d145fc6b)
![image](https://github.com/user-attachments/assets/017ba190-e579-4713-9c26-989e913e5cbc)
#### ---------------------------------------------------------------------------------------------------------------------------------
### fazer o <form> dentro do componente `create-modal`
###### que receba o input do título , preço , link url da imagem
##### em vez de criar várias tags repetidas de inputs, crie o componente de variavel constante `Input` e reutilize-o mudando apenas o props
###### faço isso dentro do componente `Input` para pegar somente a informação do valor input alterado
```
onChange={event => updateValue(event.target.value)}
```
#### ---------------------------------------------------------------------------------------------------------------------------------
### Fazer uma requisição http do tipo post na  para o endpoint `/food`
###### esta função vai mandar os dados digitados pelo cliente para o backend pelo método POST
###### dentro da pasta `src/components/hooks/` criar um ts useFoodDataMutate.ts
###### tem um problema pois o component reutilizável define que o updateValue somente receba string ou number e dentro do componente CreateModal estou passando como props para propriedade updateValue um tipo de variavel que não é nem string  e nem é number , é uma função . Eu preciso definir um tipo de dado dentro do updateValue que posse aceiar receber por props aquela variável do state que tem um função dentro dela
```
/*
Já tentei usar generics e nao da certo pois eu preciso definir o tipo de dado para cada um dos inputs
*/
import { useState } from 'react';

interface InputProps{
  label: string,
  value: string | number,
  updateValue: (value:string | number) => void; //primeira coisa digitada
  //updateValue:(value: any)=> void;// solucao da dev kipper jeito do video dela
}

const Input = ({label, value, updateValue}:InputProps)=>{
  return(
    <>
      <label>{label}</label>
      <input value={value} onChange={event => updateValue(event.target.value)}></input>
    </>
  )
}

export function CreateModal(){
  const [title, setTitle] = useState("");
  const [price, setPrice] = useState(0);
  const [image, setImage] = useState("");

  return(
    <div className="modal-ovelay"> // serve para escurecer pedaço atrás do modal 
      <div className="modal-body"> // dentro dessa div vai ficar o formulário
        <h2>Cadastre um novo item no cardápio</h2>
        <form className="input-container">
          //erro updateValue esta esperando receber numero ou string, estou passando por props uma função
          <Input label="title" value={title} updateValue={setTitle}  />
          <Input label="price" value={price} updateValue={setPrice}  />
          <Input label="image" value={image} updateValue={setImage}  />
        </form>
      </div>

    </div>
  )
}
```
###### erro dizia , 'Dispatch<SetStateAction<number>>' e 'Dispatch<SetStateAction<string>>' não é compativel com    '(value: string | number)' , logo inclui esse tipo 'SetStateAction<number| string>'

até agora foi gastado 7h em 29' de video
encontri um bug fiz igual a kipper dev e apareceu um erro

