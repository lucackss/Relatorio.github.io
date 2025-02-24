
Capítulo 1 – Introdução aos Sistemas Operacionais

1.1 O que é um Sistema Operacional?
Um sistema operacional (SO) é um software fundamental que atua como intermediário entre o hardware do computador e os programas de usuário. Ele pode ser visto de duas formas:
-Gerenciador de recursos: Administra os componentes do sistema, como CPU, memória e dispositivos de entrada/saída (E/S), garantindo o uso eficiente desses recursos.
-Máquina estendida: Fornece uma interface abstrata para facilitar a interação do usuário com o hardware, escondendo sua complexidade. Essa abstração inclui conceitos como processos, arquivos e memória virtual.

1.2 História dos Sistemas Operacionais

A evolução dos sistemas operacionais pode ser dividida em quatro gerações:
-1.2.1 Primeira Geração (1945-1955) – Computadores Sem SO
Os primeiros computadores eram operados manualmente sem nenhum software intermediário.
A programação era feita diretamente em linguagem de máquina ou utilizando cartões perfurados.
-1.2.2 Segunda Geração (1955-1965) – Sistemas em Lote
Surgiram os primeiros sistemas operacionais rudimentares para substituir operadores humanos na execução de tarefas repetitivas.
Os sistemas em lote (batch systems) permitiam que múltiplos jobs fossem organizados em sequência, sendo processados sem interação do usuário.
Um monitor residente permanecia na memória para carregar e executar os programas automaticamente.
-1.2.3 Terceira Geração (1965-1980) – Multiprogramação
O desenvolvimento dos mainframes e a necessidade de melhor utilização dos recursos levaram à multiprogramação, permitindo a execução simultânea de múltiplos programas na memória.
Surgiram os primeiros sistemas time-sharing, possibilitando que múltiplos usuários interagissem simultaneamente com o computador por meio de terminais remotos.
Exemplos de sistemas dessa geração: IBM OS/360 e MULTICS.
-1.2.4 Quarta Geração (1980-presente) – Computadores Pessoais
A popularização dos microcomputadores trouxe sistemas operacionais voltados para usuários individuais, como MS-DOS, MacOS e Windows.
Posteriormente, sistemas operacionais ganharam suporte para interfaces gráficas (GUIs), redes e multitarefa preemptiva.
Surgiram os sistemas operacionais modernos como Windows, Linux, MacOS e Android.

1.3 Estrutura do Hardware e sua Relação com o SO

Os sistemas operacionais dependem diretamente do hardware, que é composto por:
-Processador (CPU): Executa instruções de programas e gerencia operações do sistema.
-Memória principal (RAM): Armazena dados temporários e programas em execução.
-Dispositivos de entrada/saída (E/S): Componentes como discos rígidos, teclados e monitores.
-Barramentos: Canais de comunicação que conectam os dispositivos ao processador.
O SO gerencia esses componentes garantindo que os programas acessem os recursos corretamente e evitando conflitos entre processos.

1.4 Conceitos Fundamentais dos Sistemas Operacionais

Os sistemas operacionais modernos são construídos sobre cinco conceitos essenciais:
-1.4.1 Processos
Um processo é um programa em execução, contendo código, dados e estado de execução.
O SO gerencia processos, permitindo sua criação, finalização e troca de contexto para multitarefa.
Suporte a threads, que são subdivisões de um processo para execução concorrente.
-1.4.2 Gerenciamento de Memória
Controla a alocação de memória para processos.
Utiliza memória virtual para expandir a memória física utilizando espaço em disco.
-1.4.3 Entrada/Saída (E/S)
Gerencia dispositivos de hardware como discos, impressoras e teclados.
Utiliza drivers para padronizar a comunicação entre hardware e software.
-1.4.4 Sistemas de Arquivos
Estrutura e organiza os dados em dispositivos de armazenamento.
Possui mecanismos de permissão para controle de acesso.
-1.4.5 Segurança e Proteção
Implementa mecanismos para impedir acessos não autorizados.
Utiliza criptografia, autenticação e controle de permissões.

1.5 Chamadas de Sistema (System Calls)

As chamadas de sistema são a interface entre os programas de usuário e o SO. Elas permitem que os programas executem funções essenciais do sistema operacional. No UNIX, elas são classificadas em quatro categorias:
-Gerenciamento de processos: Criar, terminar e sincronizar processos.
-Manipulação de arquivos: Criar, abrir, ler, escrever e deletar arquivos.
-Gerenciamento de diretórios: Criar e remover diretórios, listar arquivos, modificar permissões.
-Chamadas diversas: Alocar memória, configurar permissões e interagir com dispositivos.

1.6 Estruturas dos Sistemas Operacionais

Os sistemas operacionais podem ser organizados de diferentes formas para facilitar seu desenvolvimento e manutenção:
-1.6.1 Sistemas Monolíticos
O SO é escrito como um grande bloco de código, onde todos os serviços operam juntos.
Exemplo: Linux.
-1.6.2 Estrutura em Camadas
O SO é dividido em módulos organizados em camadas, onde cada camada interage apenas com a inferior.
Exemplo: THE (Technical University of Eindhoven).
-1.6.3 Micronúcleo (Microkernel)
Apenas funções essenciais (como comunicação entre processos) estão no núcleo. O restante opera no espaço do usuário.
Exemplo: Minix, QNX.
-1.6.4 Arquitetura Cliente-Servidor
O SO é dividido em pequenos servidores independentes que se comunicam por mensagens.
Exemplo: Windows NT, GNU Hurd.
-1.6.5 Máquinas Virtuais
O hardware é virtualizado para rodar múltiplos sistemas operacionais simultaneamente.
Exemplo: VMware, VirtualBox.
-1.6.6 Exonúcleo (Exokernel)
O SO oferece apenas funções mínimas, permitindo que aplicativos tenham controle direto do hardware.
Exemplo: ExOS.
