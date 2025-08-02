# Sobre o Projeto

Este é um projeto de uma plataforma de eventos, construído com uma arquitetura web full-stack. Ele permite que usuários se cadastrem, criem e gerenciem eventos, comprem ingressos e visualizem estatísticas. A aplicação utiliza um frontend reativo construído em React e um backend robusto em Node.js para servir uma API RESTful.

## ✨ Funcionalidades Principais

*   **Autenticação de Usuários**: Sistema completo de registro e login com diferentes perfis (administrador, organizador, participante).
*   **Gerenciamento de Eventos**: Organizadores podem criar, editar e visualizar seus próprios eventos.
*   **Compra de Ingressos**: Participantes podem visualizar eventos e adquirir ingressos.
*   **Roteamento Protegido**: O acesso a determinadas páginas é restrito com base no perfil do usuário logado.
*   **Upload de Imagens**: Funcionalidade para upload de imagens para os eventos, utilizando um parser especializado no backend.
*   **Painel Administrativo**: Área exclusiva para administradores gerenciarem a plataforma.

---

## 🛠️ Tecnologias Utilizadas

O projeto é dividido em duas partes principais: **Frontend** (client-side) e **Backend** (server-side).

### Backend (Server-side)

O backend é responsável pela lógica de negócio, gerenciamento de dados e segurança.

*   **[Node.js](https://nodejs.org/)**: Ambiente de execução JavaScript que permite construir aplicações de servidor escaláveis.
*   **[Express.js](https://expressjs.com/pt-br/)**: Framework minimalista para Node.js, utilizado para criar a API RESTful, gerenciar rotas (`/api/events`, `/api/users`, etc.) e middlewares.
*   **Formidable**: Biblioteca de alta performance para Node.js, especializada em analisar dados de formulários (`multipart/form-data`). É a tecnologia chave para processar os uploads de imagens dos eventos de forma eficiente.
*   **bcrypt.js**: Essencial para a segurança, esta biblioteca é usada para fazer o *hash* das senhas dos usuários antes de salvá-las no banco de dados, prevenindo que senhas sejam armazenadas em texto plano.

### Frontend (Client-side)

O frontend é uma **Single Page Application (SPA)**, proporcionando uma experiência de usuário rápida e fluida.

*   **React**: Biblioteca JavaScript para construir interfaces de usuário componentizadas e declarativas. É a base de toda a interface do projeto.
*   **React Router**: Utilizado para gerenciar a navegação e o roteamento do lado do cliente. Ele permite criar URLs distintas para cada página (`/login`, `/events/:id`) sem a necessidade de recarregar a página inteira.
*   **React Context API**: Usado para o gerenciamento de estado global, principalmente no `AuthContext`. Ele permite compartilhar dados de autenticação (como o usuário logado e seu token) entre todos os componentes da aplicação de forma simples e eficiente.
*   **CSS**: Utilizado para a estilização dos componentes, garantindo uma aparência visual coesa e agradável, como visto no arquivo `App.css`.

---

Alunos: Tomaz 
        Roberto 
