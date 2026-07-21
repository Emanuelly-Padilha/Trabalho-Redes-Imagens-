# Exercício 2 - Gerenciador de Relacionamentos Pessoais (Monica HQ)

Este repositório contém a configuração e orquestração da aplicação **Monica HQ** utilizando Docker Compose.

##  Sobre a Aplicação
O [Monica HQ](https://www.monicahq.com/) é um sistema de gerenciamento de relações pessoais (CRM Pessoal) em código aberto. Ele permite organizar contatos, interações, datas importantes e notas.

- **Imagem Utilizada:** `monica:latest` (Docker Hub)
- **Banco de Dados:** `mysql:8.0` (Docker Hub)

---

## Configurações Realizadas

### 1. Isolamento de Rede e Portas
- **Rede Interna:** Criada a rede bridge `monica_network` para comunicação entre o banco de dados e a aplicação.
- **Portas:** Apenas a porta da aplicação Web (`8080:80`) está exposta para o host. O banco MySQL opera exclusivamente internamente, garantindo maior segurança.

### 2. Persistência de Dados
Foram definidos dois volumes nomeados no `compose.yaml`:
- `mysql_data`: Persiste as tabelas, cadastros e dados do banco de dados MySQL.
- `monica_data`: Persiste os arquivos, uploads e storage da aplicação PHP.

---

##  Como Executar a Aplicação

### Pré-requisitos
- Docker e Docker Compose instalados.

### Passos:
1. Clone este repositório.
2. Certifique-se de ter um arquivo `.env` configurado na raiz (utilize o modelo abaixo se necessário):

```env
DB_DATABASE=monica
DB_USERNAME=monica_user
DB_PASSWORD=senha_segura_banco
MYSQL_ROOT_PASSWORD=senha_root_banco
APP_KEY=base64:4T3x9kLqZ1mP8vW2yX0jR5nS7uA6cB1dE8fG9hI0jK1=
APP_URL=http://localhost:8080