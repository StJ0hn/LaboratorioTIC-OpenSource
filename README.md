# Estudo de Soluções Open Source de TIC

> Projeto de Iniciação Acadêmica — Bolsa de Pesquisa  
> Universidade | Vigência: 9 meses

---

## Objetivo

Substituir os logins genéricos compartilhados nos computadores de laboratório da universidade por um sistema de **autenticação centralizada e individualizada**, integrado ao sistema acadêmico **SIGAA**, com suporte a monitoramento de atividade dos usuários nas máquinas do laboratório.

---

## Escopo Técnico

A solução é baseada integralmente em software **open source** e envolve as seguintes tecnologias:

| Componente | Função |
|---|---|
| **OpenLDAP / Samba AD DC** | Diretório centralizado de identidades |
| **SSSD** | Integração entre o diretório e o sistema operacional |
| **PAM + libpam-mkhomedir** | Autenticação e criação automática de diretórios home |
| **Virtualização (VirtualBox)** | Montagem do ambiente de laboratório para testes |
| **SIGAA** | Sistema acadêmico da universidade (backend de identidade existente) |

---

## Estrutura do Repositório

```
.
├── README.md
├── atividade-01/               # Ambiente virtualizado (Linux + Windows em rede)
│   ├── screenshots/
│   ├── notas.md
│   └── configs/
├── atividade-02/               # Servidor Headless e IP Estático
│   └── ...
├── atividade-03/               # Servidor de Ficheiros (Samba) e Snapshots
│   └── ...
└── docs/
    ├── arquitetura.md          # Diagramas e decisões de arquitetura
    └── referencias.md          # Materiais de estudo e fontes
```

---

## Atividades

### Atividade 01 — Montagem do Ambiente Virtualizado
- Instalação do VirtualBox no Fedora Linux (host)
- Criação de VM Linux (Debian/Ubuntu)
- Criação de VM Windows
- Configuração de rede interna com comunicação entre as VMs

### Atividades futuras
- A definir com o orientador conforme o andamento do projeto

---

## Ambiente de Desenvolvimento

- **Host**: Fedora Linux (dual boot com Windows)
- **Hypervisor**: Oracle VirtualBox (Tipo 2)
- **CPU**: Intel Core i5 — 13ª Geração
- **RAM**: 32 GB
- **Armazenamento disponível (Fedora)**: ~100 GB

---

## Status do Projeto

🟡 Em andamento — Fase inicial de montagem do laboratório virtual

---

## 👤 Autor

**John Miguel** — Bolsista de Iniciação Acadêmica  
Orientado por **Wesley Saraiva** — Técnico Universitário