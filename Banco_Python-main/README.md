🚀 IWS: Desvendando o Poder das APIs REST com FastAPI

Este repositório apresenta o trabalho desenvolvido na disciplina de IWS, focado na compreensão e implementação de uma API RESTful completa. O projeto principal é uma API de Gerenciamento de Pedidos construída com FastAPI e padrões de projeto limpos.

🧐 O que é uma API REST e como ela funciona?

O coração deste projeto é a aplicação dos princípios REST (Representational State Transfer). A arquitetura REST utiliza os padrões e protocolos da web, especialmente o HTTP, para se comunicar.

🧩 Processo Básico

Conceito

Descrição

Exemplo

Recursos

Tudo na API é um recurso (usuário, livro, pedido), identificado por uma URL única.

https://api.exemplo.com/usuarios/123

Métodos HTTP

Verbos que definem a ação a ser executada sobre o recurso.

GET/pedidos
<img width="1280" height="1024" alt="Get_listarpedidos" src="https://github.com/user-attachments/assets/7683d5df-b320-4053-b361-db45853795c4" />
GET/pedidos{pedidos_id}
<img width="1280" height="1024" alt="Ler_pedido" src="https://github.com/user-attachments/assets/89d6e9c8-6d0b-454f-86e5-528516d0a72a" />
POST/pedidos
<img width="1280" height="1024" alt="Criar_pedido" src="https://github.com/user-attachments/assets/ea49fa70-d09b-43a0-bb57-42508dad0fdb" />
PUT/pedidos{pedido_id}
<img width="1280" height="1024" alt="Criar_pedido" src="https://github.com/user-attachments/assets/33990464-9467-490e-bbc1-32736b054551" />
DELETE/pedidos{pedidos_id}
<img width="1280" height="1024" alt="Deletar_pedido" src="https://github.com/user-attachments/assets/4dcac849-a669-488a-8332-e93a09db7f7b" />


Formato de Dados

Padrão leve e legível para troca de dados.

JSON (JavaScript Object Notation)

Status Codes

Códigos de resposta do servidor que indicam o resultado da operação.

200 OK, 201 Created, 404 Not Found

🎯 Métodos HTTP e Ações (CRUD)

O protocolo HTTP é a espinha dorsal, utilizando seus métodos para mapear as operações de CRUD (Create, Read, Update, Delete) em nossos recursos:

Método HTTP

Operação CRUD

Ação

GET

Read (Leitura)

Recupera dados de um recurso.

POST

Create (Criação)

Cria um novo recurso.

PUT / PATCH

Update (Atualização)

Atualiza um recurso existente.

DELETE

Delete (Exclusão)

Remove um recurso.

🛠️ Detalhes da Implementação (API de Gerenciamento de Pedidos)

O projeto implementa uma API para gerenciar clientes, pedidos e itens de pedido, seguindo uma arquitetura modular.

🏗️ Estrutura do Projeto

A organização do código foi pensada para seguir o princípio da responsabilidade única, facilitando a manutenção e a escalabilidade:

IWS/
├── rest/
│   ├── controllers/      # Lógica de controle (recebe requisição, chama serviço)
│   ├── models/           # Definição dos modelos de dados (SQLAlchemy)
│   ├── repositories/     # Lógica de persistência de dados (CRUD com o BD)
│   └── schemas/          # Estruturas de validação de dados (Pydantic)
├── app.py                # Ponto de entrada da aplicação FastAPI
└── ...


🛣️ Endpoints Principais (Início Rápido)

A API oferece os seguintes caminhos para interagir com os recursos de Clientes e Pedidos:

Recurso

Método

Caminho

Descrição

Cliente

GET

/clientes/{cliente_id}

Busca um cliente específico.

Cliente

POST

/clientes

Cria um novo cliente.

Cliente

PUT

/clientes/{cliente_id}

Atualiza um cliente existente.

Cliente

DELETE

/clientes/{cliente_id}

Remove um cliente.

Pedido

POST

/pedidos

Cria um novo pedido (com itens).

Pedido

GET

/pedidos/{pedido_id}

Busca um pedido e seus detalhes.

Pedido

GET

/pedidos

Lista todos os pedidos.

⚙️ Como Executar o Projeto

Para rodar a API localmente e testar os endpoints:

Clone o repositório:

git clone [SEU_LINK_DO_REPOSITORIO]
cd nome-do-seu-projeto


Crie e ative um ambiente virtual:

python -m venv venv
source venv/bin/activate  # No Linux/Mac
venv\Scripts\activate     # No Windows


Instale as dependências:

pip install -r requirements.txt
# (Ou instale manualmente: pip install fastapi uvicorn sqlalchemy pydantic)


Inicie o servidor Uvicorn:

python app.py
# Ou use o uvicorn diretamente, se preferir: uvicorn app:app --reload


A API estará disponível em http://localhost:8000.

Você pode acessar a documentação interativa gerada automaticamente pelo FastAPI em:
👉 http://localhost:8000/docs
