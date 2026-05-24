# Proposta de configuração do futuro sistema

## Visão geral

Esta proposta organiza uma base simples para o sistema, com frontend, backend, banco de dados e infraestrutura em nuvem. A ideia é deixar claro quais tecnologias serão usadas e como o projeto será separado por ambientes.

## Objetivos

- Definir uma base inicial clara para o projeto.
- Organizar as tecnologias principais que serão usadas.
- Separar o sistema em ambientes de teste e produção.
- Manter uma estrutura fácil de entender e evoluir.

## Escopo

- Frontend com Vite + React + TypeScript
- Backend com NestJS + TypeScript
- Banco de dados PostgreSQL
- Cache com Redis
- Armazenamento de arquivos com S3
- Integrações externas como Stripe, ViaCEP e serviço de e-mail
- Automação com GitHub Actions
- Ambientes: `staging` e `production`

## Stack e escolhas principais

- Backend: `NestJS`
- Frontend: `Vite` + `React` + `TypeScript`
- Banco de dados: `PostgreSQL`
- ORM: `Prisma`
- Cache: `Redis`
- Storage: `S3`
- Containerização: `Docker`
- Nuvem: `AWS`
- Automação: `GitHub Actions`

## Controle de versão e fluxo de trabalho

- Branch principal: `main`
- Criação de branches para novas funcionalidades
- Uso de pull requests para revisão antes de juntar mudanças
- Tags para marcar versões importantes

## Infraestrutura na AWS

- Uso da AWS para hospedar a aplicação
- Frontend em um serviço de arquivos estáticos, com distribuição global quando necessário
- Backend em servidores ou containers na nuvem
- Banco de dados PostgreSQL gerenciado
- Cache Redis gerenciado
- Armazenamento de arquivos no S3
- Controle de segredos com serviços da AWS
- Monitoramento básico com CloudWatch

## CI/CD (GitHub Actions)

- Uso de fluxos automáticos para validar o projeto utilizando a metodologia Trunk Based Development
- Em pull requests, rodar build e testes
- Em `main`, preparar a publicação da versão final
- Possibilidade de deploy manual quando necessário

## Testes

- Testes unitários no frontend e no backend
- Testes de interação entre componentes e serviços no frontend e backend (e2e)
- Testes de integração front-back com banco local quando necessário
- Testes manuais de ponta a ponta em ambiente de staging

## Integrações e serviços externos

- Pagamentos com Stripe
- Consulta de CEP com ViaCEP
- Envio de e-mails com Amazon SES ou SendGrid
- Armazenamento de arquivos com S3
- Uso de Redis para apoio em cache e sessão

## Observabilidade e monitoramento

- Registro de logs para acompanhamento do sistema (auditable logs)
- Métricas básicas para identificar erros e instabilidades
- Alertas simples para situações importantes

## Segurança

- Uso de HTTPS em todas as partes do sistema
- Guarda de informações sensíveis em serviços seguros da AWS
- Controle de acesso por permissões
- Revisão básica de segurança nas rotinas de integração

## Backups e recuperação

- Backups automáticos do banco de dados
- Cópias de segurança dos arquivos importantes
- Plano simples de recuperação em caso de falha

## Escalabilidade e resiliência

- Estrutura preparada para crescer aos poucos
- Possibilidade de aumentar recursos conforme a necessidade
- Uso de cache para melhorar desempenho

## Boas práticas / libs recomendadas

- Validação de dados com bibliotecas comuns do NestJS
- Configuração por variáveis de ambiente
- Uso do Prisma para acesso ao banco
- Requisições HTTP com a API nativa do projeto

## Ambientes

- `staging`: ambiente para testes e validações
- `production`: ambiente final para uso real
