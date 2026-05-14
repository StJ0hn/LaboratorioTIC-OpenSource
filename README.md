# Autenticação Centralizada e Infraestrutura de Laboratórios (Soluções Open Source de TIC)

> **Status:** Em desenvolvimento ativo (Fase de implantação de infraestrutura e serviços de rede locais)

Projeto de pesquisa e infraestrutura para substituição de logins genéricos em computadores de laboratório por um sistema de autenticação centralizada e individualizada.

## Objetivo
Desenvolvido como Projeto de Iniciação Acadêmica com o intuito de solucionar o problema de segurança e falta de rastreabilidade gerado pelo compartilhamento de credenciais. A solução propõe uma arquitetura baseada integralmente em software open source para integrar a autenticação das máquinas ao sistema acadêmico existente (SIGAA), garantindo acesso individual e monitoramento de atividades na rede.

## Stack Tecnológico e Componentes
* KVM / virt-manager (Hypervisor no Host Fedora)
* OpenLDAP / Samba AD DC (Diretório de identidades)
* SSSD e PAM / libpam-mkhomedir (Autenticação e criação de diretórios)
* Debian (Servidor Headless) e Windows 10 (Cliente)

## Arquitetura e Funcionalidades Principais
A infraestrutura está sendo construída em fases num ambiente isolado antes da implantação real. As características atuais da arquitetura incluem:
* Criação de rede virtualizada operando em modo isolado para simulação do laboratório.
* Provisionamento de servidores Linux em modo headless com padronização de IPs estáticos.
* Implementação de repositórios de arquivos via Samba para interoperabilidade entre os ambientes Windows e Linux.
* Sistema de contingência baseado em snapshots (qcow2) para validação segura de novas configurações.

## Estrutura do Repositório e Execução
Como o escopo envolve infraestrutura, este repositório armazena os registros de configuração, topologia de rede e notas técnicas. A replicação do ambiente exige o uso do KVM/QEMU.

* /atividade-01: Configurações do ambiente virtualizado em rede isolada.
* /atividade-02: Scripts e notas do provisionamento do servidor headless e endereçamento estático.
* /atividade-03: Implementação de partilha de arquivos e snapshots.
* /docs: Diagramas de arquitetura, decisões técnicas e referências.

## Desafios Técnicos e Aprendizados
As etapas iniciais exigiram um aprofundamento rigoroso em administração de sistemas e redes. A transição para o KVM/libvirt demandou a configuração manual de switches virtuais para garantir o isolamento da rede de testes. Além disso, a configuração temporária de conectividade via Cabo Duplo NAT em um servidor headless Debian consolidou conhecimentos práticos em roteamento, manipulação de interfaces de rede e gestão de pacotes via terminal puro.

## Próximas Etapas
O projeto segue em expansão sob a orientação da coordenação do laboratório. As próximas fases documentadas incluirão:
* Implantação e configuração do serviço de diretório (OpenLDAP / Samba AD).
* Integração das máquinas clientes ao domínio.
* Vinculação com o backend de identidade do sistema acadêmico.

---
Projeto de Iniciação Acadêmica
Bolsista: John Miguel
Orientador: Wesley Saraiva
