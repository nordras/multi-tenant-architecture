# Multi-Tenant Architecture

Uma arquitetura multi-tenant escalável usando AWS com isolamento por schema.

## 📋 Documentação

- [🏗️ Diagrama da Arquitetura](./arquitecture.mmd)
- [📊 Análise Detalhada](./architecture-analysis.md)
- [🚀 Auto Scaling](./autoscaling-analysis.md)
- [⚙️ Definições dos Serviços AWS](./definicoes.md)

## 🎯 Características Principais

- **Multi-tenancy**: Isolamento por schema no banco de dados
- **Escalabilidade**: ECS Fargate com auto-scaling
- **Observabilidade**: CloudWatch + Grafana
- **CI/CD**: CodePipeline + CodeBuild
- **Segurança**: Cognito + ALB + WAF

## 🏛️ Componentes da Arquitetura

### Frontend
- **Web App**: React
- **Mobile**: Android (Kotlin) + iOS (Swift)

### Backend
- **Load Balancer**: ALB (Application Load Balancer)
- **Authentication**: AWS IAM Identity Center (SSO)
- **Container Orchestration**: ECS Fargate
- **Microservices**: API, Doc, Video, Transcription, Stream, Reporting

### Data Layer
- **Database**: Aurora RDS com schemas por tenant
- **Search**: OpenSearch Service
- **Storage**: Amazon S3

### Observability
- **Monitoring**: CloudWatch
- **Dashboards**: Grafana
- **Logging**: Centralized logs

## 🚀 Deployment

O projeto utiliza AWS CodePipeline para CI/CD automatizado:

1. **Build**: CodeBuild compila e testa o código
2. **Deploy**: CodePipeline faz deploy no ECS Fargate
3. **Monitor**: CloudWatch monitora a aplicação

## 📈 Escalabilidade

- **Multi-AZ**: Deploy em múltiplas zonas de disponibilidade
- **Auto-scaling**: Baseado em métricas de CPU/memória
- **Database**: Aurora com read replicas automáticas
