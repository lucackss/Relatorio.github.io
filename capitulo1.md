Capítulo 1 – Introdução aos Sistemas Operacionais

1.1 O que é um Sistema Operacional?
Um sistema operacional (SO) é um software essencial que atua como intermediário entre o hardware do computador e os programas de usuário. Ele pode ser compreendido sob duas perspectivas principais. Primeiramente, como um gerenciador de recursos, cuja função é administrar os componentes do sistema, como a CPU, a memória e os dispositivos de entrada e saída, garantindo o uso eficiente desses recursos. Em segundo lugar, pode ser visto como uma máquina estendida, pois fornece uma interface que simplifica a interação do usuário com o hardware, abstraindo sua complexidade. Essa abstração inclui elementos como processos, arquivos e memória virtual.

1.2 História dos Sistemas Operacionais
A evolução dos sistemas operacionais acompanha o desenvolvimento da computação e pode ser dividida em quatro gerações distintas:

Primeira Geração (1945-1955) – Computadores sem SO: Nos primórdios da computação, os computadores não possuíam sistemas operacionais e eram programados diretamente em linguagem de máquina, utilizando cartões perfurados para entrada de dados. A execução de cada tarefa demandava intervenção manual, tornando o processo lento e ineficiente.

Segunda Geração (1955-1965) – Sistemas em Lote: Com o aumento da demanda por automação, surgiram os primeiros sistemas operacionais rudimentares, que substituíram operadores humanos na execução de tarefas repetitivas. Os sistemas em lote (batch systems) permitiam a execução sequencial de múltiplos programas (jobs), sem a necessidade de intervenção contínua do usuário. Além disso, um monitor residente permanecia na memória, sendo responsável por carregar e executar os programas automaticamente.

Terceira Geração (1965-1980) – Multiprogramação: O desenvolvimento dos mainframes e a necessidade de otimizar o uso dos recursos levaram à adoção da multiprogramação, técnica que permite a execução simultânea de múltiplos programas na memória. Foi nesse período que surgiram os primeiros sistemas time-sharing, possibilitando a interação simultânea de múltiplos usuários por meio de terminais remotos. Exemplos notáveis dessa geração incluem o IBM OS/360 e o MULTICS.

Quarta Geração (1980-presente) – Computadores Pessoais: A popularização dos microcomputadores levou ao desenvolvimento de sistemas operacionais voltados para usuários individuais, como o MS-DOS, MacOS e Windows. Com o passar do tempo, esses sistemas evoluíram para oferecer interfaces gráficas intuitivas, suporte a redes e capacidade de multitarefa preemptiva. Atualmente, sistemas como Windows, Linux, MacOS e Android são amplamente utilizados em diferentes plataformas.

1.3 Estrutura do Hardware e sua Relação com o SO
Os sistemas operacionais dependem diretamente da estrutura do hardware para gerenciar seus recursos de forma eficiente. Os principais componentes de um computador incluem:

Processador (CPU): Responsável pela execução das instruções dos programas e pelo gerenciamento das operações do sistema.
Memória principal (RAM): Armazena temporariamente dados e programas em execução, garantindo acesso rápido às informações necessárias.
Dispositivos de entrada/saída (E/S): Englobam componentes como discos rígidos, teclados, monitores e impressoras, permitindo a comunicação entre o usuário e o sistema.
Barramentos: Estruturas que interligam os diversos componentes do computador, possibilitando a troca de dados entre eles.
O sistema operacional gerencia esses elementos para garantir que os programas possam acessar os recursos do sistema de maneira eficiente e sem conflitos.

1.4 Conceitos Fundamentais dos Sistemas Operacionais
Os sistemas operacionais modernos se baseiam em cinco pilares fundamentais, que garantem seu funcionamento eficiente e seguro:

Gerenciamento de Processos: Um processo corresponde a um programa em execução, contendo seu código, dados e estado de processamento. O sistema operacional gerencia sua criação, finalização e troca de contexto, permitindo a multitarefa e a execução concorrente. Além disso, há suporte para threads, que são subdivisões de um processo que podem ser executadas paralelamente.

Gerenciamento de Memória: Controla a alocação e o uso da memória pelos processos. Para otimizar o uso da RAM, muitos sistemas operacionais utilizam memória virtual, técnica que expande a capacidade da memória física ao utilizar o espaço em disco como extensão temporária.

Entrada/Saída (E/S): Administra a comunicação entre o processador e os dispositivos de hardware, garantindo que operações como leitura e gravação de arquivos ocorram corretamente. O sistema utiliza drivers para padronizar a comunicação entre software e hardware.

Sistemas de Arquivos: Estruturam e organizam os dados armazenados nos dispositivos de memória, fornecendo um sistema hierárquico para o gerenciamento de arquivos e diretórios. Além disso, possuem mecanismos para controle de permissões e segurança.

Segurança e Proteção: Implementam mecanismos para impedir acessos não autorizados e garantir a integridade do sistema. Métodos como criptografia, autenticação e controle de permissões são empregados para proteger os dados e os processos em execução.

1.5 Chamadas de Sistema (System Calls)
As chamadas de sistema representam a interface entre os programas de usuário e o sistema operacional. Elas permitem que os programas realizem operações essenciais, como criação de processos, manipulação de arquivos e gerenciamento de diretórios. No UNIX, as chamadas de sistema são categorizadas da seguinte forma:

Gerenciamento de processos: Criar, finalizar e sincronizar processos.
Manipulação de arquivos: Criar, abrir, ler, escrever e excluir arquivos.
Gerenciamento de diretórios: Criar e remover diretórios, listar arquivos e modificar permissões.
Outras chamadas: Alocar memória, interagir com dispositivos e configurar permissões de acesso.
1.6 Estruturas dos Sistemas Operacionais
Os sistemas operacionais podem ser organizados de diferentes maneiras, dependendo do grau de modularidade e da complexidade desejada. As principais abordagens são:

Sistemas Monolíticos: Todo o sistema operacional é escrito como um único bloco de código, no qual todos os serviços operam juntos. Exemplo: Linux.
Arquitetura em Camadas: O SO é dividido em módulos organizados hierarquicamente, onde cada camada interage apenas com a camada inferior. Exemplo: THE (Technical University of Eindhoven).
Micronúcleo (Microkernel): Apenas as funções essenciais, como comunicação entre processos, permanecem no núcleo do SO, enquanto outros serviços operam no espaço do usuário. Exemplo: Minix, QNX.
Arquitetura Cliente-Servidor: O sistema operacional é fragmentado em pequenos servidores independentes, que se comunicam por meio de troca de mensagens. Exemplo: Windows NT, GNU Hurd.
Máquinas Virtuais: O hardware é virtualizado para permitir a execução de múltiplos sistemas operacionais simultaneamente. Exemplo: VMware, VirtualBox.
Exonúcleo (Exokernel): O sistema operacional fornece apenas um conjunto mínimo de funções, permitindo que os aplicativos tenham maior controle sobre o hardware. Exemplo: ExOS.
