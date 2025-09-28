# 📚 AWS CloudFormation, CloudWatch e CloudTrail

## 📖 Índice
- [CloudFormation](#cloudformation)
  - [O que é](#o-que-é)
  - [Principais características](#principais-características)
  - [Conceito de Stack](#conceito-de-stack)
  - [Passo a passo para criar a primeira Stack](#passo-a-passo-para-criar-a-primeira-stack)
- [CloudWatch](#cloudwatch)
  - [O que é](#o-que-é-1)
  - [Principais características](#principais-características-1)
  - [Casos de uso](#casos-de-uso)
- [CloudTrail](#cloudtrail)
  - [O que é](#o-que-é-2)
  - [Principais características](#principais-características-2)
- [Comparativo resumido](#comparativo-resumido)

---

## ☁️ CloudFormation

### O que é
O **CloudFormation** é um serviço de **Infraestrutura como Código (IaC)** que cria, gerencia e atualiza recursos da AWS automaticamente usando templates em JSON ou YAML. Ele **provisiona recursos na nuvem**, como EC2, S3, RDS e VPC.  
Você paga apenas pelos recursos criados, não pelo serviço CloudFormation em si.

### Principais características
- **Automação:** cria recursos de forma repetível  
- **Templates reutilizáveis:** use o mesmo template várias vezes  
- **Escalabilidade:** de recursos simples a arquiteturas complexas  
- **Controle de versão:** mantém histórico de alterações dos templates

### Conceito de Stack
Uma **stack** é um grupo de recursos criados a partir de um template. Pode ser **atualizada, replicada ou removida**.

### Passo a passo para criar a primeira Stack
1. Acesse: **Console AWS > CloudFormation > Stacks > Create stack**  
2. Escolha o método de criação:  
   - **Template pronto**: selecione um exemplo da AWS  
   - **Template personalizado**: faça upload de um arquivo JSON ou YAML  
3. Configure detalhes da stack:  
   - **Provide a stack name**: escolha um nome para sua stack  
   - **Parâmetros**: insira valores necessários para os recursos do template  
   - **Tags (opcional)**: adicione identificadores para organização  
4. Configure permissões:  
   - Escolha uma **Role do IAM** ou use a padrão  
5. Configurações avançadas (opcional):  
   - Limite de tempo (timeout), notificações SNS, rollback automático  
6. Revise todas as configurações  
7. Clique em **Create stack**  
8. Acompanhe a criação na aba **Events**  
9. Verifique os recursos na aba **Resources**  

---

## 📊 CloudWatch

### O que é
O **CloudWatch** monitora dados, logs e métricas da AWS em tempo real, fornecendo visão completa da saúde e desempenho dos sistemas.  
Métricas são eventos que ajudam a medir como os serviços estão funcionando.

### Principais características
- Monitoramento de métricas e logs  
- Dashboards visuais e personalizáveis  
- Alarmes e automações com notificações ou Lambda  
- Logs centralizados e análise interativa via **CloudWatch Logs Insights**

### Casos de uso
- Monitorar servidores e serviços (EC2, RDS, Lambda, containers)  
- Centralizar logs para auditoria e análise de problemas  
- Criar alertas e automações para responder a eventos  
- Observar aplicações e containers em tempo real  
- Testar experiência do usuário (simular acessos a sites/APIs)  
- Detectar anomalias usando padrões inteligentes  
- Otimizar custos identificando recursos ociosos ou subutilizados  

> Observação: o CloudWatch **não altera recursos**, apenas monitora. Ele pode executar ações configuradas, como acionar funções Lambda, mas não altera senhas ou configurações por conta própria.

---

## 🛡️ CloudTrail

### O que é
O **CloudTrail** registra todas as ações na conta AWS (Console, CLI, APIs, SDKs), fornecendo **auditoria, rastreabilidade e segurança**. Ele mostra **quem fez o quê, quando e de onde**.

### Principais características
- Registro completo de eventos e chamadas de API  
- Histórico de eventos (últimos 90 dias)  
- Armazenamento seguro em S3, com integração opcional ao CloudWatch  
- Insights para detectar atividades suspeitas  
- Filtragem por tempo, recurso e tipo de evento  

> Observação: o CloudTrail **não monitora eventos fora da AWS**, apenas ações dentro da nuvem.

---

## 🔍 Comparativo resumido

| Serviço           | Foco principal                               | Exemplo de uso                                           |
|------------------|----------------------------------------------|---------------------------------------------------------|
| **CloudFormation** | Provisionamento e gerenciamento de recursos | Criar EC2, S3 ou RDS automaticamente via template      |
| **CloudWatch**     | Monitoramento, métricas e alertas           | Receber alarme se a CPU da EC2 passar de 80%           |
| **CloudTrail**     | Auditoria e rastreabilidade                  | Ver quem acessou ou modificou um bucket S3             |
