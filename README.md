# api-spring-boot-alura

## 🔍 Sobre
API Rest criada no curso de Spring Boot da Alura. Consiste em uma api para um consultório medico, onde podem ser cadastrados medicos, pacientes e consultas.

## 🤖 Tecnologias
- Java
- Spring Boot
- Maven
- Jpa / Hibernate

## 📖 Documentação
A documentação foi feita utilizando a biblioteca SpringDoc, que contem o Swagger UI. Você pode usar o Swagger UI para testar os endpoints mencionados no tópico abaixo. 
Para acessá-la insira a URL: ```/swagger-ui/index.html```

## 👀 Endpoints

### /login
Aqui é onde você irá se autenticar e receber um Token JWT, que será usado para interagir com qualquer outro endpoint, sendo este o único que não é necessario. Neste projeto, para 
acessá-lo você terá que usar um email e senha específicos. Eles estarão abaixo na demonstração de como a requisição deve ser montada:

```
{
	"login": "ana.souza@voll.med",
	"senha": "123456"
}
```

### /consultas
Neste endpoint você podera marcar sua consultas, sendo ela com médicos aleatórios ou espeficos. Veja a demonstração dos dois casos:

**Método POST**

Caso o médico seja espeficicado:
```
}
	"idPaciente": 1,
	"idMedico": 1",
	"data": "2023-09-04T12:45"
}
```
Caso não seja, a especialidade deve ser especificada:

```
{
	"idPaciente": 1,
	"especialidade": "ORTOPEDIA",
	"data": "2023-09-04T12:45"
}
```

### /pacientes
É neste endpoint que você poderá criar e modificar os pacientes. Veremos a seguir os metódos http que podem ser usados:

**Metódo POST**

Usado para criação do paciente:

```
{
	"nome": "Carlos Andre",
	"email": "carlos.andre@voll.med",
	"telefone": "2092396790",
	"cpf": "12312354376",
	"endereco": {
		"logradouro": "rua 1",
		"bairro": "bom bairro",
		"cep": "23454356",
		"cidade": "Rio de Janeiro",
		"uf": "RJ",
		"complemento": "casa",
		"numero": "13"
	}
}
```

**Metódo PUT**

Usado para atualizar os dados de um paciente, os dados que podem ser atualizados são: nome, telefone e o endereço. Veja uma das formas com que a requisição deve ser montada:

Caso fossemos atualizar o nome de um paciente:
```
{
	"id": 1,
	"nome": "Carlos Reis"
}
```

**Metódo DELETE**

Aqui você pode deletar um paciente lógicamente, ou seja, ele não é excluido do banco de dados mas sim desativado.
Para fazer isso apenas inclua o id do paciente após o endpoint, por exemplo: ``` pacientes/2 ```

**Metódo GET**

Uma requisição GET exibe todos os pacientes. Dado que é uma requisição do tipo GET, não é necessário incluir um corpo na mesma.

Caso queira exibir apenas um paciente e não uma lista, inclua o id do paciente após o endpoint, por exemplo: ``` pacientes/2 ```

### /medicos
É neste endpoint que você poderá criar e modificar os pacientes. Veremos a seguir os metódos http que podem ser usados:

**Metódo POST**

Usado para criação do médico:

```
{
	"nome": "Carlos Goes",
	"email": "carlos.goes@voll.med",
	"telefone": "2099227890",
	"crm": "244764",
	"especialidade": "ORTOPEDIA",
	"endereco": {
		"logradouro": "rua 4",
		"bairro": "ruim bairro",
		"cep": "23554356",
		"cidade": "Rio de Janeiro",
		"uf": "RJ"
	}
}
```

**Metódo PUT**

Usado para atualizar os dados de um médico, os dados que podem ser atualizados são: nome, telefone e o endereço. Veja uma das formas com que a requisição deve ser montada:

Caso fossemos atualizar o nome de um médico:
```
{
	"id": 1,
	"nome": "Carlos Reis"
}
```

**Metódo DELETE**

Aqui você pode deletar um médico lógicamente, ou seja, ele não é excluido do banco de dados mas sim desativado.
Para fazer isso apenas inclua o id do médico após o endpoint, por exemplo: ``` medicos/2 ```

**Metódo GET**

Uma requisição GET exibe todos os médicos. Dado que é uma requisição do tipo GET, não é necessário incluir um corpo na mesma.

Caso queira exibir apenas um médico e não uma lista, inclua o id do médico após o endpoint, por exemplo: ``` medicos/2 ```


## 🏃 Como executar o projeto

### 📍 Requisitos para execução

- Java 17


*# clone o repositório*

```
git clone https://github.com/CrisDeniz/api-spring-boot-alura
```

*# vá para a pasta do projeto*

```
cd api-spring-boot-alura
```

*# execute o projeto*

```
mvn spring-boot:run
```

## Autor

Cristian Deniz

https://www.linkedin.com/in/cristian-deniz/
