# 🛡️ Indicators of Compromise — Operation Epic Fury

> Repositório de Indicadores de Compromisso (IoCs) relacionados à **Operação Epic Fury** e seus desdobramentos.

---

## 📌 Visão Geral

Este repositório centraliza os Indicadores de Compromisso (IoCs) identificados durante o monitoramento, análise e resposta à **Operação Epic Fury** — incluindo campanhas derivadas, infraestrutura associada e TTPs (Táticas, Técnicas e Procedimentos) dos agentes de ameaça envolvidos.

Os indicadores são destinados ao uso por equipes de **Threat Intelligence**, **SOC/Blue Team** e **CSIRT/Incident Response** para enriquecimento de alertas, hunting proativo e bloqueio preventivo.

---

## 📂 Estrutura do Repositório

```
.
├── iocs/
│   ├── network/
│   │   ├── ip_addresses.txt         # Endereços IP maliciosos
│   │   ├── domains.txt              # Domínios C2 e de distribuição
│   │   └── urls.txt                 # URLs completas observadas
│   ├── files/
│   │   ├── hashes_md5.txt           # Hashes MD5
│   │   ├── hashes_sha1.txt          # Hashes SHA-1
│   │   └── hashes_sha256.txt        # Hashes SHA-256
│   └── email/
│       ├── sender_addresses.txt     # Endereços de remetentes maliciosos
│       └── subjects.txt             # Assuntos de e-mails de phishing
├── stix/
│   └── epic_fury_bundle.json        # Bundle STIX 2.1 exportável
├── misp/
│   └── epic_fury_misp_export.json   # Export compatível com MISP
├── reports/
│   └── tlp_amber/                   # Relatórios restritos (TLP:AMBER)
├── scripts/
│   └── import_to_misp.py            # Script de importação para MISP
├── CHANGELOG.md
└── README.md
```

---

## 🔍 Cobertura dos Indicadores

| Tipo de IoC        | Quantidade | Última Atualização |
|--------------------|------------|--------------------|
| Endereços IP       | —          | —                  |
| Domínios           | —          | —                  |
| URLs               | —          | —                  |
| Hashes (MD5)       | —          | —                  |
| Hashes (SHA-256)   | —          | —                  |
| E-mails            | —          | —                  |

> ⚠️ Os valores serão atualizados conforme novos indicadores forem validados e incorporados.

---

## 🧩 Mapeamento MITRE ATT&CK

Os TTPs associados à Operação Epic Fury foram mapeados conforme o framework [MITRE ATT&CK](https://attack.mitre.org/):

| Tática              | Técnica                              | ID           |
|---------------------|--------------------------------------|--------------|
| Initial Access      | Spearphishing Attachment             | T1566.001    |
| Execution           | User Execution: Malicious File       | T1204.002    |
| Persistence         | Scheduled Task/Job                   | T1053.005    |
| Command & Control   | Application Layer Protocol: Web      | T1071.001    |
| Exfiltration        | Exfiltration Over C2 Channel         | T1041         |

> ℹ️ O mapeamento completo está disponível no bundle STIX 2.1 em `stix/`.

---

## 📦 Formato dos Dados

Os indicadores são disponibilizados em múltiplos formatos para facilitar integração:

- **TXT** — Listas planas para importação direta em firewalls, SIEMs e proxies
- **STIX 2.1** — Bundle estruturado para plataformas de TI compatíveis
- **MISP JSON** — Export nativo para importação direta no MISP

---

## 🚀 Importação para o MISP

Use o script disponível em `scripts/import_to_misp.py` para importar os indicadores diretamente no MISP:

```bash
python import_to_misp.py --url https://<seu-misp> --key <sua-api-key> --file misp/epic_fury_misp_export.json
```

> Requisitos: `pymisp`, `requests`. Instale via `pip install pymisp requests`.

---

## 🏷️ Classificação TLP

| Marcação        | Aplicação                                                    |
|-----------------|--------------------------------------------------------------|
| 🟢 TLP:GREEN    | IoCs em formato de lista (IPs, domínios, hashes)            |
| 🟡 TLP:AMBER    | Relatórios de análise, contexto operacional e atribuição    |
| 🔴 TLP:RED      | Informações restritas a canais bilaterais                   |

---

## 🔄 Ciclo de Atualização

Este repositório é atualizado conforme o andamento das investigações. Consulte o [CHANGELOG.md](./CHANGELOG.md) para o histórico de atualizações e novos indicadores adicionados.

---

## ⚠️ Aviso Legal

Os indicadores contidos neste repositório são fornecidos **exclusivamente para fins defensivos**. O uso deste material para qualquer atividade ofensiva é expressamente proibido. Os IoCs devem ser validados no contexto do seu ambiente antes de qualquer ação de bloqueio em produção.

---

## 📬 Contato

Para reportar falsos positivos, contribuir com novos indicadores ou solicitar acesso a relatórios TLP:CLEAR, entre em contato com a equipe de **Threat Intelligence**.