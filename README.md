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
