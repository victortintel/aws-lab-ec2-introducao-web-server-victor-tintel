# Introdução ao Amazon EC2 — Web Server com User Data, Security Group, Monitoramento e Redimensionamento

> Laboratório prático da AWS para criar, monitorar, redimensionar e encerrar com segurança uma instância **Amazon EC2** executando um **servidor web**.

##  Visão geral

Este laboratório apresenta uma visão prática de como **executar, redimensionar, gerenciar e monitorar** uma instância do Amazon EC2.  
Você irá:
- Iniciar um **web server** com **proteção contra encerramento**;
- **Monitorar** a instância (Status Checks/CloudWatch);
- **Modificar** o Security Group para liberar **HTTP (porta 80)**;
- **Redimensionar** a instância (tipo) e o **volume EBS**;
- **Testar** a proteção contra encerramento e encerrar a instância com segurança.

>  **Duração estimada:** ~45 minutos

---

##  Serviços e recursos usados

- **Amazon EC2** (instâncias, tipos, user data, termination protection)
- **Amazon EBS** (volume raiz)
- **Security Groups** (regras de entrada HTTP)
- **Amazon CloudWatch** (métricas/monitoramento básico)
- **EC2 Instance Screenshot** (solução de problemas)

---

##  Arquitetura

Uma instância EC2 dentro de uma **Availability Zone**, protegida por um **Security Group**.  
O **User Data** instala e inicia o Apache (httpd) e publica uma página simples.

---

## Resultados obtidos:

- Instância EC2 criada com proteção contra encerramento e Apache via User Data.
- Security Group atualizado para permitir HTTP (80).
- Monitoramento verificado (Status Checks e métricas básicas no CloudWatch).
- Redimensionamento da instância (t3.micro → t3.small) e do EBS (8 → 10 GiB).
- Proteção contra encerramento validada antes de terminar a instância.

---
## Aprendizados:

- User Data acelera provisionamento e configuração inicial.
- Security Groups funcionam como firewall stateful (entrada/saída).
- Status checks distinguem problemas de sistema vs. instância.
- Redimensionar tipo de instância e volume EBS é simples e reduz custos.
- Termination protection evita exclusão acidental em produção.
---

## Descrição Detalhada:

Este laboratório teve como objetivo compreender na prática o funcionamento do Amazon Elastic Compute Cloud (Amazon EC2) — um dos principais serviços da AWS — e experimentar todo o ciclo de vida de uma instância: criação, configuração, monitoramento, redimensionamento e encerramento controlado.

O Amazon EC2 é um serviço que fornece capacidade computacional redimensionável na nuvem, permitindo que desenvolvedores e administradores criem servidores virtuais com controle total sobre o ambiente. Essa flexibilidade é essencial para arquiteturas escaláveis, de alta disponibilidade e com custo sob demanda — características fundamentais da computação em nuvem moderna.

Durante a prática, foi criada uma instância EC2 configurada para atuar como um servidor web Apache (HTTPD). A instalação e inicialização do serviço foram automatizadas utilizando User Data, um recurso que permite a execução de scripts no momento da inicialização da instância. Com apenas alguns comandos bash, o servidor foi configurado para exibir uma página HTML simples, demonstrando o provisionamento automatizado de infraestrutura e software, um conceito central no DevOps e em Infraestrutura como Código (IaC).

Além da configuração inicial, foi ativada a proteção contra encerramento (Termination Protection) — uma funcionalidade importante que impede o encerramento acidental de instâncias críticas. Essa proteção adiciona uma camada de segurança operacional, garantindo que ações administrativas inadvertidas não resultem em perda de recursos ou interrupção de serviços.

O laboratório também explorou a criação e modificação de grupos de segurança (Security Groups), que atuam como firewalls virtuais controlando o tráfego de entrada e saída das instâncias. Inicialmente, a instância estava isolada sem permissão de acesso HTTP, e foi necessário ajustar as regras de entrada para liberar a porta 80 (HTTP), permitindo o acesso público à aplicação web. Essa etapa reforça a importância do gerenciamento de segurança em ambientes cloud, um aspecto essencial para administradores e arquitetos de nuvem.

Outro ponto fundamental abordado foi o monitoramento de instâncias através das verificações de status (Status Checks) e do Amazon CloudWatch. Esses recursos permitem identificar falhas no sistema e monitorar métricas como CPU, disco, rede e status operacional. O CloudWatch é um serviço crucial para acompanhar a saúde e o desempenho de recursos em produção, possibilitando o uso de dashboards e alarmes para alertas automáticos.

Em seguida, o exercício demonstrou o redimensionamento de instâncias — tanto em termos de tipo (de t3.micro para t3.small) quanto em capacidade de armazenamento (de 8 GiB para 10 GiB). Essa flexibilidade evidencia a principal vantagem da computação em nuvem: a possibilidade de escalar recursos verticalmente ou horizontalmente de acordo com a demanda, sem a necessidade de reconfigurações físicas ou longos períodos de inatividade.

Por fim, o laboratório mostrou como testar e desativar a proteção contra encerramento antes de terminar a instância. Esse processo reforça o ciclo completo de gestão de recursos na AWS, desde o provisionamento até o encerramento seguro, passando por práticas de governança e boas políticas operacionais.

Ao longo dessa experiência, foi possível compreender de forma integrada como o EC2 se relaciona com outros serviços da AWS (EBS, CloudWatch, Security Groups, IAM) e como a automação e o monitoramento tornam a administração de servidores em nuvem mais eficiente, segura e escalável.

Essa prática representa um passo essencial para profissionais de dados, DevOps e desenvolvedores que desejam dominar a infraestrutura como serviço (IaaS), pois ensina na prática os conceitos fundamentais de gestão de instâncias, segurança, monitoramento e escalabilidade. Além disso, solidifica a mentalidade cloud-first, baseada em automação, observabilidade e boas práticas de custo-benefício — pilares indispensáveis para qualquer carreira em computação em nuvem.
