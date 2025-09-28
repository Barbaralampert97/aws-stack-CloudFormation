# 🌐 AWS CloudFormation, CloudWatch & CloudTrail

---

## 📖 Índice
- [☁️ CloudFormation](#-cloudformation)
  - [O que é](#o-que-é)
  - [Principais características](#principais-características)
  - [Conceito de Stack](#conceito-de-stack)
  - [Passo a passo para criar a primeira Stack](#passo-a-passo-para-criar-a-primeira-stack)
- [📊 CloudWatch](#-cloudwatch)
  - [O que é](#o-que-é-1)
  - [Principais características](#principais-características-1)
  - [Casos de uso](#casos-de-uso)
- [🛡️ CloudTrail](#-cloudtrail)
  - [O que é](#o-que-é-2)
  - [Principais características](#principais-características-2)
- [🔍 Comparativo resumido](#-comparativo-resumido)

---

## ☁️ CloudFormation

### ✨ O que é
O **CloudFormation** é um serviço de **Infraestrutura como Código (IaC)** que cria, gerencia e atualiza recursos da AWS automaticamente usando **templates JSON ou YAML**.  
Ele provisiona recursos na nuvem (EC2, S3, RDS, VPC) sem criar arquivos locais.  
💰 **Custo:** você paga apenas pelos recursos criados, não pelo CloudFormation em si.

### 🚀 Principais características
- **Automação:** cria recursos de forma repetível  
- **Templates reutilizáveis:** use várias vezes o mesmo template  
- **Escalabilidade:** de recursos simples a arquiteturas complexas  
- **Controle de versão:** mantém histórico de alterações dos templates

### 📦 Conceito de Stack
Uma **stack** é um grupo de recursos criados a partir de um template.  
Pode ser **atualizada, replicada ou removida** conforme necessário.

### 🛠️ Passo a passo para criar a primeira Stack
1. **Console AWS > CloudFormation > Stacks > Create stack**  
2. Escolha o método de criação:  
   - **Template pronto:** selecione um exemplo da AWS  
   - **Template personalizado:** faça upload de JSON ou YAML  
3. Configure detalhes da stack:  
   - **Stack name:** escolha um nome  
   - **Parâmetros:** insira valores necessários  
   - **Tags (opcional)**  
4. Configure permissões:  
   - Escolha **Role do IAM** ou use padrão  
5. Configurações avançadas (opcional):  
   - Timeout, notificações SNS, rollback automático  
6. Revise todas as configurações  
7. Clique em **Create stack**  
8. Acompanhe na aba **Events**  
9. Verifique recursos na aba **Resources**  

---

## 📊 CloudWatch

### ✨ O que é
O **CloudWatch** monitora **dados, métricas e logs** da AWS em tempo real.  
🔹 **Métricas:** eventos que ajudam a medir o desempenho de serviços.  
💡 Dá visão completa da saúde do sistema e permite ações automáticas via alarmes ou Lambda.

### 🚀 Principais características
- Monitoramento em tempo real  
- Dashboards visuais e personalizáveis  
- Alarmes e automações via Lambda ou notificações  
- Logs centralizados e análise interativa com **CloudWatch Logs Insights**

### 📝 Casos de uso
- Monitorar EC2, RDS, Lambda e containers  
- Centralizar logs para auditoria e análise  
- Criar alertas e automações  
- Observar aplicações e containers em tempo real  
- Testar experiência do usuário (simular acessos)  
- Detectar anomalias automaticamente  
- Otimizar custos identificando recursos ociosos  

> ⚠️ CloudWatch **não altera recursos**; ele apenas monitora e executa ações configuradas.

---

## 🛡️ CloudTrail

### ✨ O que é
O **CloudTrail** registra todas as ações na conta AWS (Console, CLI, APIs, SDKs).  
🔍 Mostra **quem fez o quê, quando e de onde**.

### 🚀 Principais características
- Registro completo de eventos e chamadas de API  
- Histórico de eventos (últimos 90 dias)  
- Armazenamento seguro em S3, integração opcional com CloudWatch  
- Insights para detectar atividades suspeitas  
- Filtragem por tempo, recurso e tipo de evento  

> ⚠️ CloudTrail **não monitora eventos externos** à AWS.

---

## 🔍 Comparativo resumido

| Serviço           | Foco principal                               | Exemplo de uso                                           |
|------------------|----------------------------------------------|---------------------------------------------------------|
| ☁️ **CloudFormation** | Provisionamento e gerenciamento de recursos | Criar EC2, S3 ou RDS automaticamente via template      |
| 📊 **CloudWatch**     | Monitoramento, métricas e alertas           | Receber alarme se CPU da EC2 passar de 80%             |
| 🛡️ **CloudTrail**     | Auditoria e rastreabilidade                  | Ver quem acessou ou modificou um bucket S3             |
