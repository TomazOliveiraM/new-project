# Sobre o Projeto

1. Visão Geral do Projeto
O "Gerenciador de Eventos" é uma aplicação web completa (Full Stack) projetada para criar, gerenciar e participar de eventos. A plataforma atende a três tipos de usuários distintos, cada um com permissões e funcionalidades específicas:

Participante: Pode navegar pelos eventos, ver detalhes e adquirir ingressos.
Organizador: Pode criar, editar e gerenciar seus próprios eventos, além de visualizar estatísticas de participação.
Administrador: Possui controle total sobre a plataforma, incluindo o gerenciamento de todos os eventos e usuários.
2. Tecnologias Utilizadas
A arquitetura do projeto é baseada no stack MERN (MongoDB, Express, React, Node.js), uma escolha moderna e robusta para aplicações web.

Backend
Runtime: Node.js
Framework: Provavelmente Express.js (inferido pela estrutura de API e uso de middlewares).
Banco de Dados: MongoDB, hospedado na nuvem com o serviço MongoDB Atlas.
Autenticação:
Baseada em Token: JSON Web Tokens (JWT) para proteger as rotas da API.
Login Social: Integração com Google OAuth 2.0 para um login rápido e seguro.
Upload de Arquivos: A presença da dependência formidable indica que o backend está preparado para receber uploads de arquivos (ex: imagens de eventos), tratando dados multipart/form-data.
Gerenciamento de Ambiente: Uso da biblioteca dotenv para carregar variáveis de ambiente a partir de um arquivo .env, separando as configurações sensíveis do código-fonte.

Frontend
Biblioteca: React.js
Roteamento: react-router-dom para gerenciar a navegação entre as diferentes páginas da aplicação.
Estilização: CSS customizado, importado através do arquivo App.css.
Gerenciamento de Estado/Autenticação: Um AuthProvider (mencionado no App.jsx como estando em main.jsx) provavelmente gerencia o estado de autenticação do usuário em toda a aplicação.
3. Funcionalidades Detalhadas
A aplicação possui um sistema de rotas bem definido, com controle de acesso baseado em papéis (Roles).

Rotas Públicas (Acessíveis a todos)
/: Página Inicial (HomePage) - A porta de entrada da aplicação.
/login: Página de Login (LoginPage) - Onde os usuários se autenticam.
/register/:role?: Página de Registro (RegisterPage) - Permite o cadastro de novos usuários, possivelmente com a opção de escolher um papel (ex: organizador).
/events: Lista de Eventos (EventsListPage) - Exibe todos os eventos disponíveis.
/events/:id: Detalhes do Evento (EventDetailsPage) - Mostra informações detalhadas sobre um evento específico.
/unauthorized: Página de Acesso Negado (UnauthorizedPage) - Para onde usuários são redirecionados se tentarem acessar uma rota protegida sem permissão.
Rotas Protegidas (Requerem Login e/ou Papel Específico)
O componente ProtectedRoute é o guardião que garante que apenas usuários autorizados acessem estas rotas.

Para Organizadores e Admins (allowedRoles={['admin', 'organizador']})
/events/new: Criar Novo Evento (EventFormPage) - Formulário para adicionar um novo evento.
/events/edit/:id: Editar Evento (EventFormPage) - O mesmo formulário, mas para atualizar um evento existente.
/my-events: Meus Eventos (MyEventsPage) - Lista de eventos criados pelo organizador logado.
/organizer/stats: Estatísticas do Organizador (OrganizerStatsPage) - Dashboard com dados e métricas sobre os eventos do organizador.
Para Participantes e Admins (allowedRoles={['participante', 'admin']})
/my-tickets: Meus Ingressos (MyTicketsPage) - Exibe os ingressos que o participante adquiriu.
Apenas para Admins (allowedRoles={['admin']})
/admin: Painel do Administrador (AdminPage) - Área administrativa com funcionalidades de gerenciamento global.
Rota Geral Protegida
/dashboard: Dashboard (Dashboard) - Uma página geral para usuários logados.
4. Análise do Backend (.env)
O arquivo .env revela a espinha dorsal da configuração do servidor:

MONGO_URI: Conecta a aplicação a um cluster do MongoDB Atlas, garantindo escalabilidade e segurança para o banco de dados. Uma conexão local também está preparada para desenvolvimento.
JWT_SECRET: Um segredo forte e único usado para assinar e verificar os tokens de autenticação, garantindo a integridade das sessões dos usuários.
GOOGLE_CLIENT_ID e GOOGLE_CLIENT_SECRET: Credenciais para a API do Google, que permitem a funcionalidade de "Login com Google".
GOOGLE_CALLBACK_URL: A URL no backend para a qual o Google redireciona o usuário após a autenticação bem-sucedida.
FRONTEND_URL: Essencial para a configuração de CORS (Cross-Origin Resource Sharing), permitindo que apenas o seu frontend faça requisições à API.
PORT: Define a porta em que o servidor backend irá rodar (porta 5000).


Alunos: Tomaz /
        Roberto 
