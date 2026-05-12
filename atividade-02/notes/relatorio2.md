## Atividade 02 — Implementação de Servidor Headless e Endereçamento Estático

### Objetivo da Atividade
Provisionar uma nova máquina virtual baseada em Linux (Debian) para atuar de forma dedicada como servidor, operando sem interface gráfica (modo headless). Adicionalmente, padronizar a topologia de rede através da transição do modelo DHCP para o endereçamento IP estático em todas as máquinas do laboratório, garantindo a estabilidade e previsibilidade necessárias para a futura implementação de serviços.

#### Metodologia e Execução

Provisionamento do Servidor Linux (Headless):

- Foi criada uma nova VM no virt-manager alocando 1 GB de RAM e 20 GB de disco virtual no formato dinâmico qcow2.
- A interface de rede foi conectada à rede isolada (rede-interna-labsUFC-teste).

- Durante a instalação do sistema operativo Debian 13, a interface gráfica (Ambiente de Desktop) foi desmarcada. Foram instalados apenas os utilitários Padrão do Sistema e o Servidor SSH, resultando num sistema leve, seguro e operado exclusivamente via terminal.

Configuração de IPs Estáticos (Rede Isolada):
- Para evitar alterações dinâmicas de endereço e assegurar que os clientes encontram sempre o servidor, estabeleceu-se a seguinte padronização de IPs estáticos (máscara 255.255.255.0):

Servidor Debian: Configurado com o IP 192.168.100.10 editando manualmente o ficheiro /etc/network/interfaces. Foi necessária a validação rigorosa da sintaxe de configuração (address, netmask) e o reinício da interface com o comando ifup.

Cliente Debian: Configurado com o IP 192.168.100.20 através do NetworkManager (Interface Gráfica).

Cliente Windows 10: Configurado com o IP 192.168.100.30 nas Propriedades do Adaptador Ethernet IPv4.

Validação e Tratamento de Erros:

Testes de conectividade (ping) foram realizados entre as três máquinas.

Constatou-se uma falha de comunicação inicial do servidor para o Windows. O diagnóstico revelou que a transição para um IP estático alterou o perfil de segurança do Windows para "Rede Pública", ativando o bloqueio de pacotes ICMP no Windows Defender Firewall. O bloqueio foi resolvido, restaurando a comunicação total da rede em Camada 3.

Conclusão da Atividade 02
A infraestrutura base encontra-se agora perfeitamente delineada. O servidor headless foi implementado com sucesso e o esquema de endereçamento estático garante que os futuros serviços de rede poderão ser acedidos de forma consistente e ininterrupta pelas máquinas clientes.