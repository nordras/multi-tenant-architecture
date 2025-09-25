# Definições dos Serviços AWS

## 🛡️ **Segurança e Autenticação**

### **AWS WAF (Web Application Firewall)**
- **Função**: Proteção contra ataques web comuns
- **Características**:
  - Filtragem de requisições HTTP/HTTPS
  - Proteção contra OWASP Top 10
  - Rate limiting por IP/região
  - Geo-blocking
- **Benefícios**: Segurança na camada 7, prevenção de DDoS

### **AWS Application Load Balancer (ALB)**
- **Função**: Distribuição de tráfego HTTP/HTTPS
- **Características**:
  - Roteamento baseado em conteúdo (path, host, headers)
  - Suporte a WebSockets
  - Integração nativa com ECS/EC2
  - Health checks avançados
  - Multi-AZ deployment
- **Benefícios**: Alta disponibilidade, escalabilidade automática

### **AWS IAM Identity Center (SSO)**
- **Função**: Autenticação e autorização centralizada
- **Características**:
  - Single Sign-On (SSO)
  - Integração com Active Directory
  - SAML 2.0 e OIDC support
  - Multi-factor authentication (MFA)
  - Permission sets granulares
- **Benefícios**: Gestão centralizada de identidades, suporte enterprise

## 🚀 **CI/CD Pipeline**

### **AWS CodeCommit**
- **Função**: Repositório Git gerenciado
- **Características**:
  - Git repositories privados
  - Integração nativa com AWS
  - Controle de acesso via IAM
  - Encryption em repouso e trânsito
- **Benefícios**: Seguro, escalável, sem limites de repositórios

### **AWS CodeBuild**
- **Função**: Serviço de build e testes
- **Características**:
  - Containers Docker personalizáveis
  - Builds paralelos
  - Cache de dependências
  - Integração com artifacts
- **Benefícios**: Pay-per-use, escalabilidade automática

### **AWS CodeDeploy**
- **Função**: Deployment automatizado
- **Características**:
  - Blue/Green deployments
  - Rolling deployments
  - Rollback automático
  - Integration com ECS/Lambda/EC2
- **Benefícios**: Zero-downtime deployments, rollback rápido

### **AWS CodePipeline**
- **Função**: Orquestração de CI/CD
- **Características**:
  - Workflows visuais
  - Integração multi-serviços
  - Approval gates
  - Parallel execution
- **Benefícios**: Automação end-to-end, visibilidade completa

## 🐳 **Container Orchestration**

### **Amazon ECS Fargate**
- **Função**: Container orchestration serverless
- **Características**:
  - Sem gerenciamento de infraestrutura
  - Auto scaling baseado em métricas
  - Integration com ALB
  - Task definitions flexíveis
- **Benefícios**: Serverless, pay-per-task, segurança isolada

## 🗄️ **Armazenamento de Dados**

### **Amazon RDS (Relational Database Service)**
- **Função**: Banco de dados relacional gerenciado
- **Características**:
  - Multi-AZ deployment
  - Read replicas automáticas
  - Backup automático
  - Patch management automático
- **Benefícios**: Alta disponibilidade, backup automático

### **Amazon Aurora**
- **Função**: Banco MySQL/PostgreSQL compatível
- **Características**:
  - Performance 5x superior ao MySQL
  - Aurora Serverless v2
  - Global Database
  - Automatic scaling storage
- **Benefícios**: Performance superior, serverless scaling

### **Amazon ElastiCache**
- **Função**: Cache in-memory
- **Características**:
  - Redis e Memcached
  - Cluster mode
  - Backup e restore
  - Multi-AZ replication
- **Benefícios**: Latência ultra-baixa, alta disponibilidade

### **Amazon S3**
- **Função**: Object storage
- **Características**:
  - Storage classes múltiplas
  - Lifecycle policies
  - Versioning
  - Cross-region replication
- **Benefícios**: Durabilidade 99.999999999%, storage ilimitado

### **Amazon OpenSearch**
- **Função**: Search e analytics engine
- **Características**:
  - Full-text search
  - Log analytics
  - Dashboards Kibana
  - Machine learning insights
- **Benefícios**: Search avançado, analytics em tempo real

## 📊 **Observabilidade e Monitoramento**

### **Amazon CloudWatch**
- **Função**: Monitoramento e observabilidade
- **Características**:
  - Métricas customizadas
  - Logs centralizados
  - Alarmes automáticos
  - Dashboards visuais
- **Benefícios**: Visibilidade completa, alerting automático

### **Grafana (Self-managed)**
- **Função**: Dashboards avançados
- **Características**:
  - Visualizações customizáveis
  - Multiple data sources
  - Alerting avançado
  - Plugins extensíveis
- **Benefícios**: Dashboards profissionais, flexibilidade total

## 🔄 **Comunicação Tempo Real**

### **Amazon Chime SDK**
- **Função**: Comunicação em tempo real
- **Características**:
  - Voice/Video calling
  - Screen sharing
  - Chat messaging
  - Recording capabilities
- **Benefícios**: APIs simples, escalabilidade global

## 🏗️ **Service Discovery**

### **AWS Cloud Map**
- **Função**: Service discovery e DNS
- **Características**:
  - Service registry
  - Health checking
  - DNS-based discovery
  - API-based discovery
- **Benefícios**: Descoberta automática de serviços, health checking

## 🔧 **Auto Scaling**

### **AWS Application Auto Scaling**
- **Função**: Scaling automático para diversos serviços
- **Características**:
  - Target tracking scaling
  - Step scaling
  - Scheduled scaling
  - Multiple metrics support
- **Benefícios**: Otimização de custos, performance consistente

## 📈 **Resumo de Custos Estimados**

| Serviço | Tier | Custo Estimado/Mês |
|---------|------|-------------------|
| **ALB** | Standard | $20-50 |
| **ECS Fargate** | 2 vCPU, 4GB | $100-300 |
| **RDS** | db.t3.medium | $50-100 |
| **Aurora** | Serverless v2 | $30-150 |
| **S3** | Standard | $10-50 |
| **CloudWatch** | Standard | $20-100 |
| **WAF** | Basic rules | $10-30 |
| **IAM Identity Center** | Free | $0 |
| **CodePipeline** | Basic | $5-20 |

**Total Estimado**: $245-800/mês (varia com uso)

## 🎯 **Alternativas Consideradas**

### **Autenticação (em vez de Cognito)**
- ✅ **AWS IAM Identity Center**: Escolhido - Enterprise SSO
- ❌ **Keycloak**: Descartado - Requer gerenciamento
- ❌ **Auth0**: Custo alto para multi-tenant
- ❌ **Firebase Auth**: Vendor lock-in não-AWS

### **Justificativa IAM Identity Center**
1. **Enterprise Ready**: SSO nativo, AD integration
2. **Multi-tenant**: Permission sets por tenant
3. **Compliance**: SAML, OIDC, MFA nativo
4. **Custo**: Gratuito até 5 users, depois $0.018/user/mês
5. **Integração**: Nativa com todos serviços AWS

## 🔄 **Multi-Tenancy Strategy**

### **Schema-Level Isolation**
- **RDS**: Schemas separados por tenant
- **S3**: Bucket policies por tenant
- **IAM**: Permission sets por tenant tier
- **CloudWatch**: Custom metrics por tenant

### **Benefits**
- ✅ **Isolamento**: Dados separados logicamente
- ✅ **Custo**: Compartilhamento de infraestrutura
- ✅ **Backup**: Per tenant backup/restore
- ✅ **Compliance**: Auditoria separada por tenant

## 📚 Referências e Fontes Oficiais

### Documentação Oficial dos Serviços
- AWS WAF: https://docs.aws.amazon.com/waf/latest/developerguide/
- Application Load Balancer (ALB): https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html
- IAM Identity Center (AWS SSO): https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html
- AWS CodeCommit: https://docs.aws.amazon.com/codecommit/latest/userguide/welcome.html
- AWS CodeBuild: https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html
- AWS CodeDeploy: https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html
- AWS CodePipeline: https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html
- Amazon ECS (Fargate): https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html
- Amazon RDS: https://docs.aws.amazon.com/rds/index.html
- Amazon Aurora: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html
- Amazon ElastiCache: https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/WhatIs.html
- Amazon S3: https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
- Amazon OpenSearch Service: https://docs.aws.amazon.com/opensearch-service/latest/developerguide/what-is.html
- Amazon CloudWatch: https://docs.aws.amazon.com/cloudwatch/
- Grafana (Docs): https://grafana.com/docs/grafana/latest/
- Amazon Chime SDK: https://docs.aws.amazon.com/chime-sdk/latest/dg/what-is-chime-sdk.html
- AWS Cloud Map: https://docs.aws.amazon.com/cloud-map/latest/dg/what-is-cloud-map.html
- AWS Application Auto Scaling: https://docs.aws.amazon.com/autoscaling/application/userguide/what-is-application-auto-scaling.html
- ECS Service Auto Scaling: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html
- Aurora Serverless v2: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html
- Multi-AZ (RDS/Aurora): https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html
- AWS Chime Pricing: https://aws.amazon.com/chime/pricing/

### Boas Práticas e Guias
- Well-Architected Framework: https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html
- Well-Architected SaaS Lens: https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/
- Multi-Tenant Data Partitioning (AWS Blog): https://aws.amazon.com/blogs/
- Security Best Practices (IAM): https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
- WAF Security Automations: https://aws.amazon.com/solutions/implementations/aws-waf-security-automations/

### Custos e Planejamento
- Pricing ALB: https://aws.amazon.com/elasticloadbalancing/pricing/
- Pricing ECS Fargate: https://aws.amazon.com/fargate/pricing/
- Pricing RDS: https://aws.amazon.com/rds/pricing/
- Pricing Aurora: https://aws.amazon.com/rds/aurora/pricing/
- Pricing ElastiCache: https://aws.amazon.com/elasticache/pricing/
- Pricing S3: https://aws.amazon.com/s3/pricing/
- Pricing OpenSearch: https://aws.amazon.com/opensearch-service/pricing/
- Pricing CloudWatch: https://aws.amazon.com/cloudwatch/pricing/
- Pricing WAF: https://aws.amazon.com/waf/pricing/
- Pricing CodePipeline: https://aws.amazon.com/codepipeline/pricing/
- Pricing CodeBuild: https://aws.amazon.com/codebuild/pricing/
- Pricing CodeCommit: https://aws.amazon.com/codecommit/pricing/
- Pricing CodeDeploy: https://aws.amazon.com/codedeploy/pricing/
- IAM Identity Center Pricing: https://aws.amazon.com/singlesignon/pricing/

### Observações sobre Custos
- Valores variam por região; sempre validar na região alvo (ex: us-east-1 vs sa-east-1).
- Custos de transferência de dados (Data Transfer OUT) não incluídos e podem se tornar relevantes em streaming/video.
- CloudWatch Logs e métricas customizadas podem escalar significativamente — aplicar retenção e filtros.
- OpenSearch exige sizing cuidadoso (evitar sobreprovisionamento; considerar UltraWarm/Cold Storage).

### Notas
- As descrições de funções e características foram sintetizadas a partir da documentação oficial AWS (links acima).
- Estimativas de custo são intervalos típicos para ambientes de desenvolvimento inicial e cargas moderadas; produção de alto volume deve ser modelada com AWS Pricing Calculator: https://calculator.aws/#/
- Estratégias multi-tenant baseadas em isolamento por schema seguem recomendações recorrentes do SaaS Lens e padrões de redução de blast radius.

