# Desafio Back-end Clube do Java 🍵

Obrigado pelo interesse em participar do desafio técnico do Clube do Java! 
Este desafio tem como objetivo avaliar suas habilidades em desenvolvimento backend utilizando Java.

## Avisos antes de começar

- Leia com atenção todas as instruções.
- Crie um repositório no seu GitHub **sem citar nada relacionado ao Clube do Java**.
- Faça seus commits no repositório seguindo boas práticas de versionamento.
- Após finalizar, envie o link do projeto como issue .
- Você pode utilizar qualquer framework com o qual tenha familiaridade.
- Sinta-se livre para perguntar qualquer dúvida aos recrutadores.

## Objetivo: Plataforma de Gestão de Freelancers

A plataforma permitirá que clientes cadastrem projetos e freelancers possam se candidatar para realizá-los. 
O sistema gerenciará as propostas, permitirá negociações e registrará a finalização dos trabalhos.

### Regras de Negócio

- **Cadastro de Usuários**:
  - Dois tipos de usuários: `Cliente` e `Freelancer`.
  - Dados obrigatórios: Nome Completo, CPF/CNPJ, E-mail (único) e Senha.
  - Um usuário pode ser tanto cliente quanto freelancer, mas deve escolher um perfil principal.
  
- **Cadastro de Projetos**:
  - Somente clientes podem cadastrar projetos.
  - Um projeto deve conter título, descrição, prazo e orçamento estimado.
  - Os projetos podem ter status: `Aberto`, `Em negociação`, `Em andamento`, `Concluído` ou `Cancelado`.

- **Propostas de Freelancers**:
  - Freelancers podem se candidatar aos projetos.
  - Uma proposta deve conter o valor ofertado e prazo de entrega estimado.
  - O cliente pode aceitar ou recusar propostas.
  - Após aceitar uma proposta, o projeto muda para o status `Em andamento`.

- **Entrega do Projeto**:
  - O freelancer pode marcar o projeto como `Concluído` quando terminar o trabalho.
  - O cliente deve validar a entrega antes de mudar o status do projeto para `Finalizado`.
  - O cliente pode solicitar ajustes, voltando o status para `Em andamento`.

- **Pagamentos**:
  - Simular um gateway de pagamentos para liberar o valor do projeto ao freelancer após a conclusão e aprovação.
  - Criar um mock de serviço externo para processar pagamentos (exemplo: `POST /pagamento/autorizar`).
  - Se o pagamento falhar, o sistema deve reter o valor e tentar processar novamente.

- **Notificações**:
  - Enviar notificações por e-mail ou webhook quando:
    - Um freelancer enviar uma proposta.
    - Um cliente aceitar uma proposta.
    - Um projeto for concluído.
  - Criar um mock de serviço externo para envio de notificações (exemplo: `POST /notificacao/enviar`).

## Requisitos Técnicos

- A aplicação deve ser construída utilizando **Java 11+**.
- Utilizar **Spring Boot** ou outro framework de sua escolha.
- Banco de dados relacional (PostgreSQL, MySQL, etc.).
- API RESTful seguindo boas práticas de design de APIs.
- Implementar testes unitários e de integração.
- Uso adequado de logs e tratamento de erros.
- Documentação da API utilizando **Swagger** ou similar.

## Diferenciais

- Uso de **Docker** para ambiente de desenvolvimento.
- Arquitetura desacoplada (camadas Controller, Service, Repository, etc.).
- Implementação de mensageria com RabbitMQ ou Kafka.
- Cache para otimizar consultas frequentes.
- CI/CD com GitHub Actions ou outra ferramenta.
- Deploy automatizado para um serviço de cloud.

## Exemplo de Endpoint de Proposta

```http request
POST /propostas
Content-Type: application/json

{
  "projetoId": 10,
  "freelancerId": 3,
  "valor": 5000.00,
  "prazoDias": 30
}
```

## O que será avaliado

- Organização do código.
- Qualidade da modelagem do banco de dados.
- Clareza na implementação das regras de negócio.
- Boas práticas de desenvolvimento (SOLID, Clean Code, etc.).
- Estrutura e padronização da API.
- Documentação e testes.

Boa sorte! 🚀

