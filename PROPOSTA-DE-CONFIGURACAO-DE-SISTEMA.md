# Proposta de configuração do futuro sistema

## Visão geral

Proposta inicial alinhada à stack e requisitos solicitados: backend em NestJS, frontend com Vite + React, padronização em TypeScript, infraestrutura gerenciada via Terraform na AWS, e pipelines de CI/CD em GitHub Actions.

## Objetivos

- Estabelecer decisões técnicas claras para implementação inicial.
- Garantir práticas de alta qualidade (tests, observability, segurança).
- Criar base reprodutível com IaC (Terraform) e imagens Docker.

## Escopo

- Frontend (Vite + React + TypeScript)
- Backend (NestJS + TypeScript)
- Banco de dados relacional (PostgreSQL em RDS)
- Cache (Redis)
- Armazenamento de objetos (S3)
- Integrações externas: Stripe (pagamentos), ViaCEP (CEP), serviço de e-mail (SES/SendGrid)
- Pipelines de CI/CD com GitHub Actions (YAML)
- Ambientes: `staging` e `production` apenas

## Stack e escolhas principais

- Backend: `NestJS` (TypeScript, modular, testes com Jest)
- Frontend: `Vite` + `React` + `TypeScript` (Vitest + React Testing Library para testes unitarios e Playwright para E2E)
- ORM/DB access: `Prisma`
- Cache: `Redis` (sessions, caches, rate limits)
- Storage: `S3` (assets e backups de arquivos)
- Containerização: `Docker` para imagens reproducíveis
- IaC: `Terraform` para provisão na AWS
- CI/CD: `GitHub Actions` com workflows em YAML

## Controle de versão e fluxo de trabalho

- Branching: `main` (produção) + branches de feature. Uso de tags para releases.
- Política de merge: rebase + fast-forward para manter histórico linear.
- Pull requests obrigatórios com revisão e checks (lint, tests unitários)

## Infraestrutura na AWS (alto nível)

- Rede: VPC com subnets públicas/privadas
- CDN: `CloudFront` para frontend estático (S3 origin)
- Backend: imagens Docker rodando em `EC2` (ou ECS/EKS se for necessário evoluir)
- Balanceamento: `ALB` (Application Load Balancer) na frente das instâncias
- Banco: `RDS PostgreSQL` (multi-AZ para produção)
- Cache: `ElastiCache Redis`
- Armazenamento: `S3` (artefatos, uploads)
- Secrets: `AWS Secrets Manager` ou `SSM Parameter Store`
- Observability: CloudWatch + integração a Grafana/Prometheus/OTel se necessário

## CI/CD (GitHub Actions)

- Workflows em YAML para:
  - `push` em `main` → build + tests → deploy para `production` (controlado por tags/semver)
  - `pull_request` → build + lint + tests → deploy preview para `staging` (opcional)
  - `workflow_dispatch` para deploy manual
- Jobs recomendados: `lint`, `build`, `unit tests`, `e2e tests`, `image build` (Docker), `push image to registry`, `terraform plan/apply` (com aprovações para prod)

## Testes

- Unitários: `Vitest`/`React Testing Library` no frontend e `Vitest` no backend
- Integration: testes em banco local/containers (Postgres em Docker)
- E2E: `Playwright` rodando contra `staging` (pipeline separado)

## Integrações e serviços externos

- Pagamentos: `Stripe` (webhooks, segurança, idempotency)
- CEP: `ViaCEP` (API pública amplamente usada no Brasil)
- E-mail: `Amazon SES` (integração nativa com AWS) ou `SendGrid` (se preferir serviço independente)
- Cache/Session: `Redis` (ElastiCache em produção)
- Armazenamento de arquivos: `S3` para uploads e assets estáticos
- Fila de mensagens (opcional): RabbitMQ ou Kafka para tarefas assíncronas (e.g., envio de e-mails, processamento de pedidos)

## Observability e monitoramento

- Logs centralizados em CloudWatch + export para ELK/Grafana quando necessário
- Métricas e alertas: CloudWatch Alarms / Grafana + Prometheus

## Segurança

- HTTPS obrigatório (CloudFront + certificado ACM)
- Gerenciamento de secrets: AWS Secrets Manager
- Scans de segurança em CI (dependabot, Snyk/Trivy para imagens)
- Políticas IAM com princípio de privilégios mínimos

## Backups e recuperação

- Backups automáticos do RDS (snapshot daily) e retenção configurável
- Versionamento de objetos em S3 para proteção contra deleções acidentais
- Plano de recovery documentado com RTO/RPO esperados (definir valores)

## Escalabilidade e resiliência

- Serviços stateless em containers para escalar horizontalmente
- Uso de Auto Scaling Groups para EC2
- Estratégias de cache para reduzir latência e carga no banco

## Boas práticas / libs recomendadas

- Validação: `class-validator` + `class-transformer` (NestJS)
- Config: `@nestjs/config` / env-schema para validação de variáveis de ambiente
- Observability: `@opentelemetry/*`
- ORM: `Prisma` (migrations, type-safe queries)
- HTTP client: `fetch api` customizada com retries/circuit-breaker

## Ambientes

- `staging`: espelho controlado da produção (dados sanitizados)
- `production`: multi-AZ, monitoramento e backups ativos
