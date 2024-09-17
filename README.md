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
