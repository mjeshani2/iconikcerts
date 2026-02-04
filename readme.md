# IconikCerts 🏆

> **Modern, automation-first certificate generator platform**

IconikCerts is a powerful, scalable certificate generation platform that enables users to design, generate, print, verify, and share certificates at scale using reusable templates. Built for individual creators, educational institutions, corporations, and event organizers.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://typescriptlang.org/)
[![Next.js](https://img.shields.io/badge/Next.js-000000?logo=next.js&logoColor=white)](https://nextjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql&logoColor=white)](https://postgresql.org/)

## ✨ Key Features

### 🎨 **Smart Template Builder**
- Drag-and-drop certificate editor with real-time preview
- Dynamic text fields ({{Name}}, {{Course}}, {{Date}}, {{ID}})
- Image uploads, QR codes, and custom styling
- Lifetime reusable templates with versioning
- Alignment guides and precision tools

### ⚡ **Bulk Certificate Generation**
- Upload CSV/Excel files with recipient data
- Generate 100-10,000 certificates in one action
- Automatic ZIP download and email delivery
- Duplicate detection and validation
- Real-time progress tracking

### 🖨️ **Professional Print Studio**
- Multiple paper sizes (A4, Letter, Legal, Custom)
- Portrait/landscape orientation support
- Margin and bleed control for commercial printing
- Print-perfect PDF output with DPI optimization
- Batch print management

### 🛒 **Community Marketplace**
- Upload and monetize certificate templates
- Browse thousands of professional designs
- Rating and review system
- Creator profiles and revenue sharing
- Featured templates and collections

### 🔐 **Certificate Verification**
- Unique QR code per certificate
- Public verification pages (no login required)
- Tamper-proof certificate validation
- Personal certificate wallet for recipients
- Instant revocation capabilities

### 👥 **Team Collaboration**
- Role-based access control (Admin/Editor/Viewer)
- Team workspaces and shared templates
- Approval workflows for certificate issuance
- Usage analytics and reporting

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and npm/yarn
- PostgreSQL database
- Redis (for job queues)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/mjeshani2/iconikcerts.git
   cd iconikcerts
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   ```
   
   Configure your `.env.local` file:
   ```env
   # Database
   DATABASE_URL="postgresql://username:password@localhost:5432/iconikcerts"
   
   # NextAuth
   NEXTAUTH_URL="http://localhost:3000"
   NEXTAUTH_SECRET="your-secret-key"
   
   # File Storage (Cloudflare R2 or AWS S3)
   CLOUDFLARE_R2_ACCESS_KEY_ID="your-access-key"
   CLOUDFLARE_R2_SECRET_ACCESS_KEY="your-secret-key"
   CLOUDFLARE_R2_BUCKET_NAME="iconikcerts"
   
   # Redis (Upstash)
   UPSTASH_REDIS_REST_URL="your-redis-url"
   UPSTASH_REDIS_REST_TOKEN="your-redis-token"
   
   # Email (Optional)
   SMTP_HOST="smtp.gmail.com"
   SMTP_PORT="587"
   SMTP_USER="your-email@gmail.com"
   SMTP_PASS="your-app-password"
   ```

4. **Set up the database**
   ```bash
   npx prisma generate
   npx prisma db push
   ```

5. **Run the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🏗️ Tech Stack

### Frontend
- **Next.js 14+** - Full-stack React framework
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **shadcn/ui** - High-quality component library
- **Fabric.js** - Canvas-based certificate editor
- **Zustand** - Lightweight state management

### Backend
- **Next.js API Routes** - Serverless API endpoints
- **PostgreSQL** - Primary database
- **Prisma** - Type-safe ORM
- **BullMQ + Redis** - Job queue system
- **NextAuth.js** - Authentication

### Infrastructure
- **Vercel** - Deployment platform
- **Cloudflare R2** - File storage and CDN
- **Upstash Redis** - Serverless Redis
- **Puppeteer** - PDF generation

## 📁 Project Structure

```
iconikcerts/
├── src/
│   ├── app/                 # Next.js app directory
│   │   ├── (auth)/         # Authentication pages
│   │   ├── dashboard/      # User dashboard
│   │   ├── editor/         # Template editor
│   │   ├── marketplace/    # Template marketplace
│   │   └── verify/         # Certificate verification
│   ├── components/         # Reusable UI components
│   │   ├── ui/            # shadcn/ui components
│   │   ├── editor/        # Certificate editor components
│   │   └── dashboard/     # Dashboard components
│   ├── lib/               # Utility functions and configurations
│   │   ├── auth.ts        # NextAuth configuration
│   │   ├── db.ts          # Database connection
│   │   ├── queue.ts       # Job queue setup
│   │   └── utils.ts       # Helper functions
│   ├── types/             # TypeScript type definitions
│   └── workers/           # Background job workers
├── prisma/                # Database schema and migrations
├── public/                # Static assets
├── docs/                  # Documentation
│   ├── requirements.md    # Product requirements
│   └── design.md         # System design
└── README.md
```

## 🔧 Development

### Available Scripts

```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server

# Database
npm run db:generate  # Generate Prisma client
npm run db:push      # Push schema to database
npm run db:migrate   # Run database migrations
npm run db:studio    # Open Prisma Studio

# Code Quality
npm run lint         # Run ESLint
npm run type-check   # Run TypeScript checks
npm run format       # Format code with Prettier

# Testing
npm run test         # Run tests
npm run test:watch   # Run tests in watch mode
```

### Environment Setup

1. **Database Setup**
   - Install PostgreSQL locally or use a cloud provider
   - Create a database named `iconikcerts`
   - Update `DATABASE_URL` in your `.env.local`

2. **Redis Setup**
   - Sign up for Upstash Redis (free tier available)
   - Get your Redis URL and token
   - Update Redis configuration in `.env.local`

3. **File Storage Setup**
   - Set up Cloudflare R2 or AWS S3 bucket
   - Configure CORS for web uploads
   - Update storage credentials in `.env.local`

## 📚 Documentation

- **[Requirements Document](./requirements.md)** - Detailed product requirements and specifications
- **[System Design](./design.md)** - Technical architecture and design decisions
- **[API Documentation](./docs/api.md)** - API endpoints and usage (coming soon)
- **[Deployment Guide](./docs/deployment.md)** - Production deployment instructions (coming soon)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](./CONTRIBUTING.md) for details.

### Development Workflow

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests and linting (`npm run test && npm run lint`)
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Code Style

- Use TypeScript for all new code
- Follow the existing code style and conventions
- Write tests for new features
- Update documentation as needed

## 🚀 Deployment

### Vercel (Recommended)

1. **Connect your repository to Vercel**
2. **Configure environment variables** in Vercel dashboard
3. **Deploy** - Vercel will automatically build and deploy

### Manual Deployment

```bash
# Build the application
npm run build

# Start the production server
npm run start
```

### Environment Variables for Production

Ensure all required environment variables are set:
- Database connection string
- Authentication secrets
- File storage credentials
- Redis connection details
- Email configuration (optional)

## 📊 Roadmap

### Phase 1: MVP (Current)
- [x] Template builder with basic editor
- [x] Bulk certificate generation
- [x] PDF export and download
- [x] User authentication
- [ ] Basic print settings

### Phase 2: Community Features
- [ ] Template marketplace
- [ ] QR code verification system
- [ ] Certificate wallet for recipients
- [ ] Rating and review system

### Phase 3: Enterprise Features
- [ ] Team collaboration and RBAC
- [ ] Advanced print studio
- [ ] API access
- [ ] White-label solutions

### Phase 4: AI & Advanced Features
- [ ] AI-powered design suggestions
- [ ] Blockchain certificate anchoring
- [ ] Advanced analytics
- [ ] Mobile applications

## 🐛 Issues & Support

- **Bug Reports**: [GitHub Issues](https://github.com/mjeshani2/iconikcerts/issues)
- **Feature Requests**: [GitHub Discussions](https://github.com/mjeshani2/iconikcerts/discussions)
- **Documentation**: [Wiki](https://github.com/mjeshani2/iconikcerts/wiki)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) for the amazing full-stack framework
- [Fabric.js](http://fabricjs.com/) for the powerful canvas library
- [shadcn/ui](https://ui.shadcn.com/) for the beautiful component library
- [Prisma](https://prisma.io/) for the excellent database toolkit
- All contributors and community members

---

<div align="center">
  <p>Built with ❤️ by the IconikStudio team</p>
  <p>
    <a href="https://github.com/mjeshani2/iconikcerts">⭐ Star us on GitHub</a> •
    <a href="https://github.com/mjeshani2/iconikcerts/issues">🐛 Report Bug</a> •
    <a href="https://github.com/mjeshani2/iconikcerts/discussions">💡 Request Feature</a>
  </p>
</div>