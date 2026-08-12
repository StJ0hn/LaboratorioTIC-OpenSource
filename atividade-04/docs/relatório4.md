# Indentidades na Rede e Estudo de Active Directory
> Objetivo da Atividade
> - Analisar a viabilidade de criação de usuários e efetuar autenticação em diferentes sistemas operacionais na rede local e fundamentar base teórica sobre a arquitetura do Active Directory para implementação futura do Samba como controlador de domínio.

## Tarefa 1 --> Analisar Criação do usuário e Autenticação em Rede
1. Verificar a possibilidade de criar usuários no servidor Debian e efetuar o login através dos hosts Debian e Windows.
2. Concluiu-se que a criação de um usuário local no Linux (via comandos tradicionais no terminal) não possivilita o acesso remoto nas estações de trabalho.
3. Máquinas isoladas possuem base de dados de credenciais locais e blindadas. Um usuário criado apenas no núcleo do servidor Debian não é propagado para os hosts da rede. 

## Tarefa 2 --> Estudo do Active Directory 
- Para solucionar o problema das identidades isoladas e avançar na implementação da autenticação centralizada no laboratório, foi necessário estudar a tecnologia do Active Directory.
- Foram mapeados três pilares centrais para próxima evolução do laboratório:
    1. Domain Controller (DC): O servidor central é reponsável por gerenciar políticas de redes e autorizar logins.
    2. LDAP (Diretório): A base de dados, estrutura em formato de árvore que armazena objetos da rede (usuários, grupos e computadores).
    3. Kerberos: protocolo criptográfico focado em segurança, resposável pela autenticação entre os nós das redes.
- Papel do Samba 4:
    - Active Directory é, nativamente, uma solução proprietária atrelada às licenças da Microsoft Windows Server.
    - Por esse motivo, o Samba 4, se torna uma alternativa direta para atuar como um Active Directory Domain Controller (AC DC). Emulando o comportamento de um servidor da Microsoft, permitindo o acesso de clientes no domínio.
## Conclusão
- O laboratório encontra-se conceitualmente preparado para a promoção do serviço Samba a Controlador de Domínio, passo central para a substituição dos logins genéricos por um sistema de identidade individualizada.