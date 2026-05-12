Atividade 03 — Sistema de Snapshots e Partilha de Ficheiros (Samba)

Objetivo da Atividade
Garantir a resiliência do servidor através de ferramentas de salvaguarda (snapshots) e implementar um servidor de ficheiros centralizado utilizando o software open source Samba, promovendo a interoperabilidade e partilha de ficheiros entre os ambientes Linux e Windows na rede isolada.

Metodologia e Execução

Configuração do Sistema de Snapshots:

Utilizando as capacidades do hypervisor KVM e o formato de disco qcow2, foi capturado um instantâneo (Snapshot) do estado íntegro do servidor logo após a fixação do IP.

Esta etapa assegura um ponto de restauro imediato, prevenindo a perda de dados e evitando formatações em caso de falhas durante as configurações complexas.

Gestão de Pacotes e Conectividade Temporária:

Devido à restrição de acesso à internet da rede isolada, o servidor não conseguia obter o pacote de instalação do Samba. Foi implementada a técnica de "Cabo Duplo": uma interface virtual secundária em modo NAT foi adicionada provisoriamente para fornecer acesso externo, sendo removida após a instalação para manter o isolamento do laboratório.

Foi necessário corrigir as fontes do gestor de pacotes (/etc/apt/sources.list), desativando o repositório local do CD-ROM de instalação (cdrom://) e adicionando os repositórios oficiais da web (http://deb.debian.org/debian/).

Instalação e Configuração do Serviço Samba:

O pacote samba foi instalado com sucesso.

Foi criado um diretório partilhado (/srv/samba/arquivos_TIC) e foram atribuídas permissões totais de leitura e escrita (chmod 777) para possibilitar os testes.

O ficheiro de configuração /etc/samba/smb.conf foi alterado para mapear o diretório físico sob o nome virtual [testetic], tornando-o visível e modificável para convidados na rede. O serviço smbd foi reiniciado em seguida.

Validação de Interoperabilidade de Ficheiros:

No Windows 10: O acesso foi validado utilizando a notação padrão do protocolo SMB (\\192.168.100.10) no Explorador de Ficheiros, corrigindo tentativas anteriores de acesso via HTTP. Ficheiros foram criados com sucesso.

No Linux Debian: O acesso foi efetuado via ambiente gráfico utilizando o caminho smb://192.168.100.10, permitindo ler os ficheiros provenientes do Windows e gravar novos dados.

Conclusão da Atividade 03
A terceira fase foi concluída com um elevado grau de sucesso. As medidas de salvaguarda (snapshots) estão ativas e o servidor Samba funciona como um middleware eficiente, solucionando a barreira de comunicação entre sistemas operativos diferentes. O laboratório funciona agora como uma infraestrutura colaborativa de ficheiros, provando o valor das soluções open source na resolução de problemas do campus.