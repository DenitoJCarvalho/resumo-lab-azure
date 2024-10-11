# Resumo-lab-azure
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO.

### Computação e Rede

- Criação de máquina virtual predefinida, onde podemos escolher um ambiente de carga de trabalho, tipo de carga
- Criação de máquina virtual personalizada
- Na aba básicos precisamos informar: assinatura, grupo de recursos, nome da máquina, região, opções de disponibilidade, zona de disponibilidade, tipo de segurança, imagem, escolher tamanho da máquina, e conta de administrador
  - Opcionais: Conjunto de dimensionamneto de máquinas,
- Na aba discos foi recomendado deixar checkado a opção exlcuir com VM.
- Na aba rede deixar checkado a opção "excluir o IP e público e a NIC quando a VM foi excluída
  - Também podemos habilitar outras portas como HTTP
-  Em gerenciamento podemos habilitar **desligamento automático** e **habilitar backup**
-  Em monotoramento podemos habilitar alaertas, dignósticos, etc
-  Em avançados podemos instalar extensões


### Armazenamento

- Tipos de armazenamento:
  - Blob Storage: otimizado para armazenamento de quantidades massivas de dados não estruturados, como texto ou dados binários
  - Disco: fornece discos para máquinas virtuais, aplicativos e outros serviços acessarem
  - Fila: serviço de armazenamento de mensagens que favorece o armazenamento e recuperação para grandes quantidades de mensagens, cada uma com até 64kb
  - Arquivos: configura um comportamento  de arquivos de rede altamente disponível que pode ser utilizado usando  o protocolo _bloco de mensagens do servidor_ 

- #### Ponto de extremidade públicos
  - Blob: https://_storage-account-name_.blob.core.windows.net
  - Para cada serviço seguirá uma estrutura parecida, porém, após o _storage-account-name_ cada serviço leva seu nome ou sigla. Ex: _**.blob, .file, .dfs, etc**_

- #### Camadas de acesso do Azure
  - Frequente: otimizada para aramazenamento de acessados com frequência
  - Esporádico: para armazenamentos de dados acessados com pouca frequência e armazenado por pelo menos 30 dias
  - Frio: para armazenamento de dados acessados com pouca frequência e armazenamento por pelo menos 90 dias
  - Morto: para armazenamentos de dados acessados raramente e aramazenados por pelo menos 180 dias

- #### Opções de gerenciamneto de arquivo
  - AzCopy:
    - Utilitário de linha de comando
    - Copia blobs ou arquivos de ou para sua conta de armazenamento
    - sincroniza em uma direção

  - Gerenciador de armazenamento:
    - Interface gráfica para o usuário
    - Compatível com windows, macos e linux
    - Por debaixo dos panos faz o que o azcopy faz, mas através de uma interface mais amigável

  - Sincornização de arquivos:
    - Sincroniza os arquivos do azure e locais de forma bidirecional
    - A camada de nuvem mantém  os arquivos acessados com frequência no local, enquanto libera espaço

- ### Identidade, acesso e segurança
  - Microsoft entra ID = Active Directory
  - Serviço de gerenciamento de identidades e acesso baseado em nuvem do Microsoft Azure

  - #### SSO
    - esquema de autenticação que permite que um usuário faça login com um único ID em qualquer um dos vários sistemas de software realcionados, mas independentes
    - permite que usuário fa login uma vez acesse os serviços sem inserir novamenteos fatores de autenticação

  - #### Autenticação
    - identifica a pessoa ou serviço buscando  acesso a um recurso
    - solicita credenciais de acesso legitímo
    - base para criar princípios de identidade e controle de acesso
    - determna o nível de acesso de uma  pessoaou serviço autenticado
    - define quais dados  eles podem acessar e o que podem  fazer com eles

  - #### Autenticação Multifator
    - fornece segurança adcional para as identidades, exigiindo dois ou mais elementos para autenticação completa
    - Estatégia:
      - Algo que você sabe
      - Algo que você possui
      - Algo que você é

  - #### Acesso condicional
    - associação de usuário  ou grupo
    - local IP
    - dispositivo
    - aplicativo
    - detecção de risco

  - #### Controle de acesso baseado em função
    - gerenciamento de acesso  de granularidade fina
    - divide as tarefas dentro da equipe e concede somentea quantiadade de acesso de que os usuários precisam para trabalhar
    - habilita o acesso ao portal do azure e o controle de acesso aos recursos

  - #### Proteção
    Camadas |
    --------|
    Segurança física |
    Identidade e acesso |
    Perímetro |
    Rede |
    Computação |
    Aplicativo |
    Dados |

  - #### Microsoft Defender
    - serviço de monitoramento que fornece proteçção contra ameaças nos datacenters do azure e locais
    - **RBAC (Role-Based Access Control)**  - modelo de controle de acesso que restringe o acesso a recursos e operações com base nas funções (roles) dos usuários dentro de um sistema. Em vez de conceder permissões diretamente a cada usuário, as permissões são atribuídas a funções, e os usuários recebem essas funções. Isso facilita a administração de permissões em sistemas complexos

  #### Gerenciamento de custo  do Azure
    - envolve fatores podem afetar os custos no Azure.
    - **Fatores que afetam:**<br>
      1 - **_Tipo de recurso_**: os custos são específicos do recurso, portanto, o uso que um medidor rastreia é o número de medidores associados a um recurso, dependendo do tipo de recurso.<br>
      2 - **_Consumo_**: com um modelo pago conforme o uso, o consumo é um dos maiores geradores de custos.<br>
      3 - **_Manutenção_**: monitorar seu volume do Azure e manter seu ambiente pode ajudá-lo a identificar  e reduzir custos que não são necessários, como ao desligar máquinas virtuais subutilizadas.<br>
      4 - **_Área geográfica_**: o mesmo tipo  de recurso pode custar valores diferentes dependendo da área geográfica, o que afeta os custos do Azure.<br>
      5 - **_Tráfego de rede_**: embora algumas transferência de dados de entrada sejam gratuitas, o custo para dados de saída ou dados entre  recursos do Azure é afetado por zonas de cobrança.<br>
      6 - **_Assinaturas_**: o tipo e a configuração da assinatura também podem afetar o custo. Por exemplo a avaliação gratuita permite explorar alguns recursos do Azure gatuitamente.<br>
      7 - **_Azure Marketplace_**: permite que os clientes encontrem, experimente, comprem e provisionem aplicativos e serviços de centenas de provedores.<br>
      8 - **_Marcas_**:
          - fornecem metadados aos recursos do Azure
          - organizam os recursos em uma taxonomia de maneira lógica
          - consistem em um par nome - valor
          - muito úteis para reunir informações de cobrança  

#### Governança e Conformidade
  - **Azure Policy**:
    - padrões organizacionais e a avaliação de conformidade em escala
    - fornece governança e consistência  de recursos com conformidade regulatória, segurança, custo gerenciamento
    - Avalia e identifica os recursos que não atendem as suas politicas
    - fornece definições de políticas e iniciativas integradas, em categrias como aramazenamento, rede, computação, centralde segurança e monitoramento

  - **Bloqueio de recursos**:
    - protege os recursos de exclusão ou modificação acidental
    - gerenciar bloqueios na assinatura, grupo de recursos ou níveis de recursos individuais dentro do portal azure
   
  - **Microsoft Purview**:
    - família de soluções de governança, risco  e conformidade de dados que ajuda você a obter uma única exibição unificada em seus dados
    - reúne insights sobre seus dados locais, multinuvem e de software com serviço
    - decoberta de dados
    - classificação de dados confidenciais
    - linhagem de dados de ponta-a-ponta

#### Ferramentas de Implementação de Recursos
  - **Ferramentas para interagir com Azure**:
    • Portal do Azure
    • Azure Cloud Shell
    • Azure Power Shell
    • Interface de Linha de Comando (CLI)

  - **Azure ARC (Azure Resource Manager)**:
    - é uma extensão  do gerencimaento do Azure(local, várias nuvens e borda)
    - painel único  de gerenciamento
    - controle de acesso baseado em função
    - práticas nativas de nuvem
    - segurança e conformidade
    - fornce uma camada de gerenciamento que permite criar, atualizar e excluir recursos na assinatura do Azure
    - garante consistência na implantação em todo o sistema de nuvem
    - gerencia a confiuguraçao em escala
    - provisiona rapidamente ambientes adicionais com base em uma configuração e um build padrão
    - são arquivos JSON que podem ser usados para criar e implantar a infraestrutura do Azure sem a necessidade de escrever comandos de programação
    - _Modelos:_
      - sintaze declarativa
      - resultado repetíveis
      - orquestração
      - arquivos modulares
      - validaçao integrada
      - código exportável
     
    - **Bicep**:
      - linguagem específica de dominio (DSL) que usa sintaxe declarativa para implantar recursos do Azure
      - define a infraestrutura que deseja implantar, eme seguida, usa esse arquivo durante todo o cilco de vidade de desenvolvimento para implantar repetidamente sua infraestrutura
      - os recursos são implementados de maneira consistente
      - sintaxe concisa, segurança de tipos confiável e suporte para reutilização de código
      - compatível somente com o Azure;
