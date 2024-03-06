# Documentação do Projeto ChatDeTexto JavaSpring

## Introdução

Este projeto consiste em um sistema de mensagens semelhante ao WhatsApp, desenvolvido utilizando JavaSpring. Ele oferece funcionalidades básicas de criar usuários, criar chats entre usuários e enviar mensagens dentro desses chats.

## Estrutura do Projeto

O projeto é dividido em várias partes:

1. **Entidades**: São as classes que representam os objetos principais do sistema, como `Usuario`, `Chat`, e `Mensagem`.
   
2. **Repositórios**: São responsáveis pela comunicação com o banco de dados. Neste projeto, há três repositórios: `UsuarioRepository`, `ChatRepository`, e `MensagemRepository`.
   
3. **Controladores (Controllers)**: São responsáveis por receber as requisições HTTP e encaminhá-las para o processamento adequado. O controlador principal é o `ChatController`, responsável por gerenciar usuários, chats e mensagens.

## Funcionalidades

### 1. Criar Usuário

- **Endpoint**: `POST /chats`
- **Descrição**: Cria um novo usuário no sistema.
- **Parâmetros de entrada**: Objeto JSON representando o usuário a ser criado.
- **Código de status de retorno**: 
  - 201 (Criado) - Caso o usuário seja criado com sucesso.
  - Outros códigos de erro em caso de falha.

### 2. Criar Chat

- **Endpoint**: `POST /chats/{idUser1}/{idUser2}`
- **Descrição**: Cria um novo chat entre dois usuários existentes.
- **Parâmetros de entrada**: IDs dos dois usuários.
- **Código de status de retorno**: 
  - 201 (Criado) - Caso o chat seja criado com sucesso.
  - 404 (Não encontrado) - Caso um dos IDs de usuário não exista.

### 3. Enviar Mensagem

- **Endpoint**: `POST /chats/chat/{idChat}/user/{idUser}`
- **Descrição**: Envia uma mensagem para um chat específico.
- **Parâmetros de entrada**: ID do chat, ID do usuário remetente e objeto JSON representando a mensagem.
- **Código de status de retorno**: 
  - 201 (Criado) - Caso a mensagem seja enviada com sucesso.
  - 404 (Não encontrado) - Caso o chat ou o usuário não exista.

### 4. Ver Chat

- **Endpoint**: `GET /chats/chat/{id}`
- **Descrição**: Retorna todas as mensagens de um chat específico.
- **Parâmetros de entrada**: ID do chat.
- **Código de status de retorno**: 
  - 200 (OK) - Caso o chat seja encontrado e suas mensagens sejam retornadas.
  - 404 (Não encontrado) - Caso o chat não exista.
