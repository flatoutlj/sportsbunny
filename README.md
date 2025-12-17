# SportsBunny - Next-Generation Sports Intelligence Platform

> AI-Powered Sports Research, Analytics & Graphics Generation Engine

## Overview

SportsBunny is a comprehensive Sports Intelligence Engine that:
- Ingests sports data from multiple internet sources
- Processes and organizes data for flexible querying
- Automatically generates professional sports graphics
- Provides AI-powered research assistance
- Delivers predictive modeling and trend analysis

## Quick Start

```bash
# Install dependencies
pnpm install

# Set up environment
cp .env.example .env

# Run development server
pnpm dev

# Run all services (Docker)
docker-compose up -d
```

## Architecture

See `/docs/architecture/` for detailed system design:
- [System Overview](./docs/architecture/system-overview.md)
- [Data Pipeline](./docs/architecture/data-pipeline.md)
- [Analytics Engine](./docs/architecture/analytics-engine.md)
- [Graphics System](./docs/architecture/graphics-system.md)

## Project Structure

```
sportsbunny/
├── apps/
│   ├── web/                 # Next.js frontend
│   ├── api/                 # FastAPI backend
│   ├── graphics-service/    # Graphics generation
│   └── worker/              # Background job workers
├── packages/
│   ├── ui/                  # Shared React components
│   ├── database/            # Prisma schema & migrations
│   ├── analytics/           # Analytics computation library
│   └── types/               # Shared TypeScript types
├── docs/
│   ├── architecture/        # System architecture docs
│   ├── api/                 # API documentation
│   └── business/            # Business & monetization docs
├── infrastructure/
│   ├── terraform/           # Infrastructure as Code
│   ├── kubernetes/          # K8s manifests
│   └── docker/              # Docker configurations
└── scripts/                 # Utility scripts
```

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js 14, React 18, TailwindCSS |
| Backend | FastAPI (Python), Node.js |
| Database | PostgreSQL, TimescaleDB, Redis |
| ML/AI | Claude API, PyTorch, scikit-learn |
| Graphics | Puppeteer, Sharp, Remotion |
| Infrastructure | AWS, Kubernetes, Terraform |

## Features

### Data & Analytics
- Real-time sports data aggregation
- Player/team trend analysis
- Predictive modeling
- Natural language queries
- Custom analytics builder

### Graphics Generation
- Automated professional graphics
- Social-ready formats (16:9, 1:1, 9:16)
- Team color branding
- Static and animated outputs
- Custom template builder

### Integrations
- Discord bot
- Browser extension
- Mobile apps
- API access
- Webhook alerts

## Documentation

- [API Reference](./docs/api/README.md)
- [Graphics Templates](./docs/graphics-templates.md)
- [Query Language](./docs/query-language.md)
- [Subscription Tiers](./docs/business/pricing.md)

## License

Proprietary - All Rights Reserved
