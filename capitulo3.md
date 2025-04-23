Capítulo 3 – Gerenciamento de Memória (Resumo Detalhado)
- Introdução ao Gerenciamento de Memória
O gerenciamento de memória é essencial para permitir que múltiplos processos coexistam e executem de forma eficiente. Em sistemas simples, o gerenciamento é estático: um processo é carregado e permanece na memória até sua finalização. Esses sistemas não realizam troca (swapping) nem paginação e são comuns em sistemas embarcados ou de tempo real.

- Troca de Processos (Swapping)
Com a evolução para sistemas multiprogramáveis, tornou-se necessário permitir que mais processos residissem no sistema do que a memória física disponível. Isso é feito por meio da troca, onde processos são movidos da memória para o disco e vice-versa.

Para controlar quais áreas da memória estão livres ou ocupadas, usam-se mapas de bits ou listas de lacunas (holes).

A compactação da memória também pode ser usada para eliminar lacunas e consolidar espaço contíguo.

- Alocação de Memória
Existem várias estratégias para alocar memória:

Primeiro encaixe: escolhe a primeira lacuna grande o suficiente.

Melhor encaixe: escolhe a menor lacuna possível que ainda acomoda o processo.

Pior encaixe: escolhe a maior lacuna disponível.

Próximo encaixe: começa a busca da última posição alocada.

Esses algoritmos são testados usando exemplos de tamanhos variados de lacunas e segmentos solicitados.

- Endereços Físicos e Virtuais
Endereço físico: local real na RAM.

Endereço virtual: endereço visto pelo processo, que é traduzido por mecanismos como a TLB (Translation Lookaside Buffer) e a tabela de páginas.

A tradução de endereços é essencial para a abstração de memória.

- Paginação
A memória virtual paginada permite que o espaço de endereçamento seja dividido em páginas (do lado lógico) e quadros de página (do lado físico). Isso possibilita que páginas não contíguas sejam carregadas conforme necessário (demanda).

O tamanho das páginas (ex: 4 KB ou 8 KB) afeta a eficiência da TLB, uso de memória e número de faltas de página.

Um sistema precisa de uma TLB eficiente para reduzir acessos à tabela de páginas, que são mais lentos.

Algoritmos de substituição de página:

FIFO

LRU (Least Recently Used)

WSClock e envelhecimento são algoritmos avançados que equilibram desempenho e complexidade.

- Segmentação
A segmentação divide a memória lógica em segmentos como código, dados e pilha, com tamanhos variáveis. Isso:

Simplifica a proteção e compartilhamento de memória.

Facilita a manipulação de estruturas de dados dinâmicas. Contudo, muitos sistemas modernos (como o x86-64) abandonaram o uso ativo de segmentação.

- Paginação com Segmentação
Sistemas como o MULTICS e o antigo x86 (32 bits) combinaram paginação com segmentação, criando um esquema de memória virtual bidimensional.

Atualmente, a segmentação está em desuso, e o x86-64 suporta apenas paginação com segmentos fixos.

- Tabelas de Páginas e Estrutura de Dados
Tabelas de páginas podem ser grandes. Por isso, usam-se tabelas de páginas multinível, onde a tabela é dividida em níveis hierárquicos.

Exemplo: um endereço virtual de 32 bits pode ser dividido em partes que indicam o índice em cada nível da tabela e o deslocamento.

- Desempenho e Eficiência
O carregamento da tabela de páginas pode ocupar tempo da CPU.

O tempo de execução real de um processo pode ser impactado por faltas de página, especialmente se forem frequentes.

A técnica copy-on-write é usada para otimizar a cópia de processos, permitindo que páginas sejam compartilhadas até que uma modificação ocorra.

- Considerações de Hardware
Para que a memória virtual funcione, são necessários:

MMU (Unidade de Gerenciamento de Memória)

TLB

Suporte à tabela de páginas no hardware Sistemas antigos, como o 8086, implementavam paginação mesmo sem MMU real, usando hardware externo ou segmentação criativa.
