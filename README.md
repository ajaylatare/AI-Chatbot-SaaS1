# 🤖 AI Chatbot SaaS

A full-stack AI Chatbot SaaS application built with Angular, Express, and MySQL — similar to ChatGPT with subscription-based access to advanced AI models.

## 🌟 Features

- **User Authentication** — Register/Login with JWT tokens
- **AI Chat Interface** — ChatGPT-like UI with conversation history
- **Token Usage Tracking** — Daily token limit for free users
- **Subscription Plans** — Free (GPT-3.5) and Paid (GPT-4) plans
- **Dashboard** — View token usage and plan details
- **Responsive Design** — Built with Angular Material

## 🛠️ Tech Stack

### Frontend
- Angular 21
- Angular Material UI
- TypeScript
- RxJS

### Backend
- Node.js + Express
- JWT Authentication
- Sequelize ORM
- OpenAI API (GPT-3.5 / GPT-4)

### Database
- MySQL (Local)
- PostgreSQL/Neon (Production)

## 📁 Project Structure
ai-chatbot-saas/
├── frontend/                    # Angular 21 App
│   ├── src/
│   │   ├── app/
│   │   │   ├── auth/            # Login, Register
│   │   │   ├── chat/            # Chat UI
│   │   │   ├── dashboard/       # User Dashboard
│   │   │   ├── subscription/    # Plans & Payment
│   │   │   └── shared/          # Services, Guards
│   │   └── environments/
│   └── package.json
│
├── backend/                     # Express API
│   ├── config/                  # DB Config
│   ├── controllers/             # Business Logic
│   ├── middleware/              # Auth, Plan Check
│   ├── models/                  # Database Models
│   ├── routes/                  # API Routes
│   ├── services/                # AI, Token Services
│   ├── utils/                   # Helper Functions
│   └── server.js
│
└── README.md

## 🗄️ Database Schema
Users          → id, name, email, password, plan
Conversations  → id, title, userId
Messages       → id, role, content, tokensUsed, conversationId
Subscriptions  → id, plan, startDate, endDate, paymentId, userId
TokenUsages    → id, tokensUsed, date, userId

## 🔌 API Endpoints
AUTH
POST   /api/auth/register     → Register new user
POST   /api/auth/login        → Login user
CHAT
POST   /api/chat/conversations → Create conversation
GET    /api/chat/conversations → Get all conversations
POST   /api/chat/send         → Send message to AI
GET    /api/chat/messages/:id → Get messages
USER
GET    /api/user/profile      → Get user profile
SUBSCRIPTION
GET    /api/subscription/plans   → Get all plans
POST   /api/subscription/upgrade → Upgrade to paid plan

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- MySQL 8.0
- Angular CLI 21+

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/ajaylatare/ai-chatbot-saas.git
cd ai-chatbot-saas
```

**2. Backend Setup**
```bash
cd backend
npm install
```

Create `.env` file in backend folder:
```env
# Server
PORT=5000

# MySQL Database
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=ajay@123
DB_NAME=ai_chatbot_db

# JWT
JWT_SECRET=meri_secret_key_123456

# OpenAI
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxx
```

Start backend:
```bash
node server.js
```

**3. Frontend Setup**
```bash
cd frontend
npm install --legacy-peer-deps
ng serve
```

**4. Create MySQL Database**
```sql
CREATE DATABASE ai_chatbot_db;
```

### Access Application

Frontend → http://localhost:4200
Backend  → http://localhost:5000

## 💡 How It Works
User (Browser)
↓
Angular Frontend (port 4200)
↓ HTTP Request + JWT Token
Express Backend (port 5000)
↓
MySQL Database + Gemini AI API
↓
Response back to user

## 🔐 Security Features

- Passwords encrypted with bcrypt
- JWT token authentication
- Protected routes with Auth Guard
- SSL database connection (production)
- Environment variables for secrets

## 💰 Subscription Plans

| Feature | Free Plan | Pro Plan |
|---------|-----------|----------|
| AI Model | GPT-3.5 Turbo | GPT-4 |
| Daily Tokens | 4,000 | Unlimited |
| Price | ₹0/month | ₹499/month |

## 🎯 Demo Flow

1. Register a new account
2. Login with credentials
3. Create new chat
4. Send message to AI
5. View token usage in Dashboard
6. Upgrade plan on Plans page
7. Logout

## 👨‍💻 Developer

**Ajay Latare**
- GitHub: [@ajaylatare](https://github.com/ajaylatare)

## 📄 License

MIT License
