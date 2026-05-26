# BGstock

Sistema de gestão de estoque e realização de pedidos.

O sistema tem o intuito de agilizar e facilitar a administração do estoque de sua empresa e realizar pedidos de produtos de forma intuitiva e direta. 

---

# Visão Geral

O sistema é um gerenciador de estoque focado em pequenos comércios no qual pode-se acompanhar quantidade, categorias e tipos de produtos, o sistema também gera relatórios de entrada e saída dos produtos do estoque, alertas de estoque baixo, ou de itens avariados, também através de uma API pode-se realizar o pedido dos produtos cadastrados no estoque.

O sistema foi desenvolvido utilizando arquitetura em camadas, separando domínio, aplicação, API e interface web.

---

# Principais Funcionalidades

- Dashboard intuitiva
- Cadastro de produtos
- Controle de estoque
- Relatórios semanais do estoque
- FastAPI
- Swagger/OpenAPI
- Persistência em MySql
- Interface responsiva com Streamlit

---

# Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| FastAPI | Backend e API |
| SQLAlchemy | ORM |
| MySql | Banco de dados |
| Streamlit | Interface web |
| Swagger/OpenAPI | Documentação automática |
| Python | Linguagem principal |
| Uvicorn | Servidor ASGI |

---

# Estrutura da Solução

```txt
BGstock/
│
├── src/
│   ├── BGstock.API/
│   │   ├── routes/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   ├── database/
│   │   └── main.py
│   │   
│   ├── BGstock.Web/
│   │   └── app.py
│   │
│   └── BGstock.Core/
│
├── tests/
│   └── BGstock.Tests/
│
└── requirements.txt

```

---

# Arquitetura do Sistema

## BGstock.API

Responsável pela exposição dos endpoints da FastAPI do sistema.

Principais responsabilidades:
- gerenciamento dos estoques
- comunicação HTTP
- integração com banco de dados Mysql
- documentação Swagger
- serialização JSON

---

## BGstock.Web

Responsável pela interface do sistema.

Principais responsabilidades:
- dashboard intuitiva
- gerenciamento visual de todo o estoque
- relatórios
- navegação do sistema
- experiência do usuário

---

## BGstock.Core

Camada de domínio da aplicação.

Responsável por:
- entidades
- modelos principais
- regras centrais do negócio

---

## requirements.txt

Arquivo reponsável pela lista de dependências do projeto

```txt
fastapi
uvicorn
sqlalchemy
pymysql
streamlit
pandas
```
---

# Funcionalidades Implementadas

## Dashboard

O sistema possui um dashboard administrativo contendo:

- Campo de select para escolher qual estoque deseja gerenciar
- Interface intuitiva e direta
- Cards dinâmicos com a quantidade de itens no estoque, alertas de estoque baixo e de operadores de estoque disponíveis
- Relatórios de entrada e saída do estoque, com gráficos e amostragem de métricas intuitivas

---

## Pedidos

O módulo de pedidos permite:

- Sugestões de itens com o estoque baixo para comprar
- Campo para salvar fornecedores fixos e os itens oferecidos por eles
- Campo para realizar pedidos aos fornecedores salvos
- Campo de pesquisa com uma tabela para procurar fornecedores cadastrados com a categoria de itens, endereço e formas de contato de cada um

---

## Entregas

O módulo de entregas apresenta:

- Cards dinâmicos para visualizar estimativa de entrega, para demonstração de alertas sobre problemas na entrega ou problemas com notas fiscais
- Campo para entrar em contato com fornecedor de cada pedido
- Campo com os contatos dos órgãos responsáveis pela tributação e das empresas de logística de entrega para qualquer problema que houver na entrega

---

# Banco de Dados

O sistema utiliza MySQL para persistência dos dados do estoque, pedidos e fornecedores.

---

# Como Executar o Projeto

## Pré-requisitos

- Python
- Streamlit
- Visual Studio ou VS Code

---

# Instalar dependências

```bash
python -m venv venv
pip install -r requirements.txt
```

# Executar API

```bash
cd src/BGstock.API
python -m uvicorn main:app --reload
```

Swagger:

```txt
http://localhost:8000/docs/
```

---

# Executar Frontend Web

Abra outro terminal:

```bash
cd src/BGstock.Web
python -m streamlit run app.py
```

Acesse:

```txt
http://localhost:8501
```


---

# Endpoints da API

## Produtos

### Listar produtos

```http
GET /api/produtos
```

### Criar produto

```http
POST /api/produtos
```

### Buscar produto por ID

```http
GET /api/produtos/{id}
```

### Atualizar produto

```http
PUT /api/produtos/{id}
```

### Deletar produto

```http
DELETE /api/produtos/{id}
```

---

## Estoque

### Listar estoque

```http
GET /api/estoque
```

### Adicionar estoque

```http
POST /api/estoque
```

### Atualizar estoque

```http
PUT /api/estoque
```

### Deletar estoque

```http
DELETE /api/estoque
```

---

## Pedidos

### Ver pedidos

```http
GET /api/pedidos
```

### Realizar pedido

```http
POST /api/pedidos
```


---


Exemplo:

```json
{
  "nome": "Mouse Gamer",
  "categoria": "Periféricos",
  "quantidade": 25,
  "preco": 149.90
}
```

---

# Fluxo do Sistema

```txt
Usuário
   ↓
Interface Web (Streamlit)
   ↓
  API
   ↓
Services
   ↓
SQLAlchemy ORM
   ↓
 MySQL
```

---

# Objetivo do Projeto

O projeto foi desenvolvido para otimização da gestão do estoque

---

# Melhorias Futuras

- App Mobile
- Sistema de notificações sobre o estoque via email ou sms

---

# Licença

Projeto empresarial para fins comerciais.O projeto foi desenvolvido para otimização da gestão do estoque
