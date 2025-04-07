 O que são processos?
Um processo é um programa em execução. Diferente de um programa parado no disco, um processo tem:

Seu estado de execução (ativo, esperando ou bloqueado),

Espaço de endereçamento próprio (sua própria memória),

Recursos associados (arquivos abertos, variáveis, etc.).

Processos podem ser criados e encerrados dinamicamente, e muitos rodam ao mesmo tempo (concorrência), mesmo que pareça que o computador está executando um de cada vez. O sistema operacional simula essa execução simultânea (usando escalonamento).

🔹 Estados de um processo
Durante sua vida, um processo pode estar em três estados:

Executando: está na CPU naquele momento.

Pronto (executável): está esperando sua vez de executar.

Bloqueado: está esperando por algum recurso (ex: resposta do disco).

O sistema operacional faz a transição entre esses estados dependendo de eventos e da lógica de controle de processos.

🔹 Threads – Múltiplos fluxos de execução
Para tornar os processos mais eficientes e rápidos, surgiram as threads (ou “linhas de execução”):

São subprocessos, que compartilham o mesmo espaço de memória do processo principal.

Cada thread tem sua própria pilha, registradores e contador de programa.

Permitem que várias tarefas sejam feitas ao mesmo tempo dentro de um mesmo processo (ex: um navegador carregando uma página enquanto permite rolar a tela).

Threads são úteis, por exemplo, em programas com tarefas paralelas (como servidores web).

🔹 Tipos de Threads
Threads no espaço do usuário: gerenciadas pela aplicação, sem envolvimento direto do núcleo.

Threads no núcleo: gerenciadas diretamente pelo sistema operacional, com mais controle e interação com o hardware.

Ambas têm vantagens e desvantagens. Threads no núcleo são mais poderosas, mas também mais “caras” (mais lentas para criar/trocar). Threads no espaço do usuário são mais leves, mas o sistema operacional não as reconhece individualmente.

🔹 Comunicação e Sincronização entre Processos (e Threads)
Muitas vezes, processos ou threads precisam trabalhar juntos. Para isso, usam primitivas de comunicação:

Semáforos: variáveis especiais que controlam o acesso a recursos compartilhados.

Monitores: estruturas de dados com mecanismos de controle embutidos.

Mensagens: troca direta de informações entre processos.

Essas ferramentas evitam condições de corrida (quando dois processos tentam usar o mesmo recurso ao mesmo tempo) e permitem sincronização, garantindo que tudo funcione de forma coordenada.

🔹 Problemas clássicos de concorrência
O capítulo também discute exemplos clássicos de problemas de sincronização:

Produtor-consumidor: um produz dados enquanto outro consome; precisam se coordenar.

Jantar dos filósofos: cinco filósofos dividem talheres e devem evitar deadlocks (travamentos).

Leitor-escritor: leitores podem acessar dados simultaneamente, mas escritores precisam exclusividade.

Esses problemas mostram a importância de controlar bem a concorrência para evitar travamentos ou comportamentos errados.

🔹 Escalonamento de processos
Escalonamento é o processo de decidir qual processo/thread será executado a seguir. Há vários algoritmos para isso:

🧮 Algoritmos comuns:
FCFS (First Come, First Served): executa na ordem de chegada.

Shortest Job First: executa o menor processo primeiro.

Round-Robin: dá um “quantum” de tempo para cada processo, em ciclos.

Por prioridade: processos com maior prioridade rodam antes.

Múltiplas filas: processos são organizados por tipo ou prioridade.

Escalonamento por loteria: cada processo recebe “bilhetes” e sorteios decidem quem executa.

Proporcional Justo (fair-share): dá a cada processo uma fatia justa do tempo da CPU.

Alguns sistemas modernos separam o mecanismo de escalonamento (como funciona) da política de escalonamento (quem escolhe o que executar), permitindo mais flexibilidade e personalização.
