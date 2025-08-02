# Sobre o Projeto

🗂️ Visão Geral do Projeto
Gerenciador de Eventos é uma aplicação web Full Stack (MERN) desenvolvida para facilitar a criação, gerenciamento e participação em eventos. A plataforma possui três tipos de usuários, cada um com permissões e funcionalidades específicas:



👤 Participante:

Navega pelos eventos

Visualiza detalhes

Adquire ingressos

🧑‍💼 Organizador:

Cria, edita e gerencia seus próprios eventos

Acompanha estatísticas de participação



🛠️ Administrador:

Tem controle total da plataforma

Gerencia todos os eventos e usuários



⚙️ Tecnologias Utilizadas
📦 Backend
Runtime: Node.js

Framework: Express.js (uso de middlewares e estrutura REST)

Banco de Dados: MongoDB (MongoDB Atlas – hospedagem na nuvem)

Autenticação:

JSON Web Tokens (JWT)

OAuth 2.0 (Login com Google)

Upload de Arquivos:

Uso da biblioteca formidable para lidar com multipart/form-data

Variáveis de Ambiente:

Utilização do dotenv para separar dados sensíveis do código



💻 Frontend
Biblioteca: React.js

Roteamento: react-router-dom

Estilização: CSS customizado (via App.css)

Autenticação e Estado Global:

AuthProvider (configurado em main.jsx) para controle de autenticação



🌐 Funcionalidades e Rotas
🔓 Rotas Públicas
/: Página Inicial (HomePage)

/login: Página de Login

/register/:role?: Página de Registro (por tipo de usuário)

/events: Lista de Eventos

/events/:id: Detalhes do Evento

/unauthorized: Acesso Negado



🔐 Rotas Protegidas (com controle de acesso por papel)
👥 Para Organizadores e Administradores
/events/new: Criar Novo Evento

/events/edit/:id: Editar Evento

/my-events: Meus Eventos

/organizer/stats: Estatísticas do Organizador



🎟️ Para Participantes e Administradores
/my-tickets: Meus Ingressos

🛡️ Apenas para Administradores
/admin: Painel do Administrador

📊 Acesso Geral Protegido
/dashboard: Dashboard geral para usuários logados



O componente ProtectedRoute faz a guarda dessas rotas com base no papel do usuário (allowedRoles).

🔐 Configurações do Arquivo .env (Backend)
Variável	Função
MONGO_URI	Conecta ao banco MongoDB Atlas (com fallback local)
JWT_SECRET	Chave usada para assinar/verificar os tokens JWT
GOOGLE_CLIENT_ID	ID do cliente OAuth para login com Google
GOOGLE_CLIENT_SECRET	Segredo do cliente OAuth
GOOGLE_CALLBACK_URL	Endpoint de callback após autenticação com o Google
FRONTEND_URL	Configuração de CORS: libera apenas o frontend autorizado
PORT	Porta onde o backend será executado (ex: 5000)


Alunos: Tomaz /
        Roberto 
