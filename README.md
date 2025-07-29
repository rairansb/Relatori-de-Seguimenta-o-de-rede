# 🔐 Análise de Segmentação de Rede.


Projeto tecnico do modulo 1 da formacao-cybersec Vai na Web e Kensey, voltado para auditoria de redes segmentadas utilizando containers Docker. O objetivo é identificar falhas de segurança, má segmentação, serviços expostos e riscos de movimentação lateral em ambientes corporativos simulados.

## 📌 Objetivo

Avaliar a segurança de uma rede segmentada em três sub-redes distintas, identificando exposições indevidas de serviços e recomendando melhorias na arquitetura e proteção dos ativos de TI.

## 🧪 Ambiente Simulado

O ambiente foi criado com Docker, representando:

- 🖥️ `corp_net`: Rede de estações de trabalho (usuários finais)
- 🧰 `infra_net`: Rede de infraestrutura crítica (servidores)
- 📶 `guest_net`: Rede isolada para visitantes

Cada container simula um host real com serviços e comportamento de rede específicos.

## 🔍 Ferramentas Utilizadas

- **Nmap** – Descoberta de hosts, serviços e vulnerabilidades (com NSE)
- **Rustscan** – Escaneamento rápido de portas
- **Arp-scan / arp -a** – Mapeamento da rede local
- **Curl** – Testes manuais em servidores HTTP

## ⚙️ Metodologia

1. **Coleta ativa**: Scans de rede e reconhecimento de hosts
2. **Identificação de serviços e IPs ativos**
3. **Documentação técnica**
4. **Diagrama lógico da rede**
5. **Diagnóstico de falhas e recomendações**

## 🛡️ Diagnóstico de Segurança

### Principais riscos identificados:

- FTP anônimo ativo (`10.10.30.10`)
- MySQL exposto (`10.10.30.11`)
- LDAP sem autenticação (`10.10.30.17`)
- SMB com compartilhamentos visíveis (`10.10.30.15`)
- Painel Zabbix acessível externamente (`10.10.30.117`)

### Recomendações:

- Migrar de **FTP para SFTP**
- Restringir acesso ao **MySQL**
- Proteger **LDAP** com autenticação
- Restringir **shares SMB**
- Isolar painel **Zabbix** por VPN
- Implementar **firewall entre sub-redes**
- Implantar **IDS/IPS**

## ✅ Plano de Ação Prioritário (80/20)

| Ação                         | Impacto | Facilidade | Prioridade |
|-----------------------------|---------|------------|------------|
| Migrar FTP para SFTP        | Alto    | Alta       | Alta       |
| Restringir porta MySQL      | Alto    | Alta       | Alta       |
| Autenticar LDAP             | Alto    | Média      | Alta       |
| Restringir SMB              | Médio   | Média      | Média      |
| Isolar painel Zabbix        | Alto    | Alta       | Alta       |
| Firewall entre sub-redes    | Alto    | Baixa      | Média      |
| Implementar IDS/IPS         | Alto    | Baixa      | Média      |

## 📎 Relatório Técnico

O relatório completo com tabelas, diagnóstico e plano de ação está disponível neste repositório, recomendo fazer o download do arquivo:  
📄 [`Relatorio_Segmentacao_de_Rede.pdf`](./Relatorio_Segmentacao_de_Rede.pdf)

## 🖼️ Diagramas e Evidências

- Diagrama lógico da rede: esta no PDF e no arquivo [`redes.diagrama.html`](.resdes.diagrama.html)
- Prints dos terminais: Estão no arquivo de relatorio em PDF.
- Saídas de ferramentas: [`Estão na pasta recon-backup`](./recon-backup)

Acesse:  
📁 [github.com/rairansb/Relatori-de-Seguimenta-o-de-rede](https://github.com/rairansb/Relatori-de-Seguimenta-o-de-rede)

## 👤 Autor

**Rairan Barbosa**  
📧 [rairandesbravador@gmail.com](mailto:rairandesbravadorb@gmail.com)  
🔗 [linkedin.com/in/rairan-barbosa](https://www.linkedin.com/in/rairan-barbosa/)  
🛠️ Analista de Sistemas
