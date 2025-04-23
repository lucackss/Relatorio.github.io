Capítulo 3 – Gerenciamento de Memória (Resumo Expandido)
🔸 1. Visão Geral do Gerenciamento de Memória
A principal função do gerenciamento de memória é permitir que vários processos coexistam, maximizando o uso da RAM e oferecendo proteção, isolamento e flexibilidade. Os sistemas operacionais modernos precisam lidar com a limitação da memória física e o crescente número de processos e programas exigentes.

Nos primeiros sistemas operacionais, o gerenciamento de memória era extremamente simples: um processo era carregado por vez e permanecia na memória até o término. Não havia mecanismos de troca, paginação ou memória virtual. Esses modelos ainda são comuns em sistemas embarcados ou aplicações de tempo real, onde a previsibilidade é mais importante que a eficiência de uso da memória.

🔸 2. Multiprogramação e Swapping (Troca)
Com o advento da multiprogramação, tornou-se necessário lidar com vários processos ao mesmo tempo. Isso introduziu a ideia de swapping, onde processos inativos são removidos temporariamente da memória e armazenados no disco. Quando voltam a ser ativos, são trazidos de volta para a memória.

A memória e o disco precisam de gerenciamento:

Mapas de bits: um vetor indica se cada bloco de memória está livre ou ocupado.

Listas de lacunas: registram blocos contíguos de memória livre.

A compactação da memória é usada para eliminar lacunas e realocar os segmentos para que fiquem contíguos, mas é um processo custoso, especialmente em sistemas grandes.

Exemplo: para compactar 4 GB de memória com um acesso de 4 ns por palavra, leva-se vários segundos, o que é inaceitável em muitos contextos.

🔸 3. Técnicas de Alocação de Memória
Quando novos processos precisam ser alocados na memória, o SO pode utilizar diferentes estratégias de alocação de lacunas:

Primeiro Encaixe (First Fit): seleciona a primeira lacuna suficientemente grande.

Melhor Encaixe (Best Fit): escolhe a menor lacuna que seja suficiente.

Pior Encaixe (Worst Fit): seleciona a maior lacuna possível, esperando sobrar espaço utilizável.

Próximo Encaixe (Next Fit): variação do primeiro encaixe, continua a busca a partir do último local alocado.

Essas estratégias afetam diretamente o nível de fragmentação da memória e o desempenho do sistema.

🔸 4. Espaço de Endereçamento: Endereço Virtual x Físico
Endereço Físico: posição real na memória RAM.

Endereço Virtual: posição lógica usada pelo processo.

Os endereços virtuais são convertidos para físicos por meio da MMU (Unidade de Gerenciamento de Memória).

Isso permite que diferentes processos usem os mesmos endereços virtuais sem conflito, graças à tradução isolada.

Essa separação permite a abstração da memória contínua, mesmo que fisicamente ela esteja fragmentada.

🔸 5. Paginação e Memória Virtual
A paginação por demanda é uma das técnicas mais usadas em SOs modernos:

O espaço de endereçamento é dividido em páginas de tamanho fixo (ex: 4 KB, 8 KB, 16 KB).

A memória física é dividida em quadros de página do mesmo tamanho.

Apenas as páginas necessárias são carregadas na RAM, reduzindo o uso de memória física.

Tabela de Páginas:
Cada processo tem sua tabela de páginas, que mapeia páginas virtuais para quadros físicos.

Em sistemas grandes, usa-se tabela de páginas em múltiplos níveis para evitar tabelas muito grandes em memória.

Exemplo:

Um sistema com endereços de 32 bits e páginas de 4 KB terá 2²⁰ páginas por processo (pois 2³² / 2¹² = 2²⁰).

Se cada entrada da tabela tiver 4 bytes, a tabela ocupa 4 MB.

🔸 6. TLB – Translation Lookaside Buffer
A TLB é uma memória cache especial usada para acelerar a tradução de endereços virtuais para físicos.

Quando um endereço virtual é acessado, verifica-se primeiro a TLB:

Hit: a tradução está na TLB, e o acesso é rápido.

Miss: a tabela de páginas deve ser acessada, o que é mais lento.

A eficiência da TLB depende de:

Número de entradas (ex: 32, 64, 1024).

Localidade de referência dos programas.

🔸 7. Faltas de Página (Page Faults)
Uma falta de página ocorre quando o processo tenta acessar uma página que não está carregada na memória:

O sistema pausa a execução, busca a página no disco e a carrega.

Isso é extremamente custoso (pode levar milissegundos).

A frequência de faltas de página deve ser minimizada.

Fórmula do tempo de instrução efetivo:
*Tefetivo = (1 - p) * Tacesso + p * Tfalta*
onde p é a taxa de faltas de página.

🔸 8. Algoritmos de Substituição de Página
Quando não há mais quadros disponíveis, uma página existente deve ser substituída. Os algoritmos incluem:

FIFO: remove a página mais antiga.

LRU (Least Recently Used): remove a menos recentemente usada.

Envelhecimento: aproxima o LRU usando bits de acesso.

WSClock: balanceia uso recente e tempo de residência, ideal para sistemas modernos.

🔸 9. Segmentação
A segmentação divide o espaço de endereçamento em segmentos de tamanho variável (código, dados, pilha).

Permite melhor proteção e compartilhamento.

Facilita manipulação de estruturas dinâmicas.

Apesar de suas vantagens, a segmentação está caindo em desuso:

Os sistemas modernos preferem paginação pura.

O x86-64, por exemplo, praticamente abandonou o uso real da segmentação.

🔸 10. Combinação de Paginação e Segmentação
Alguns sistemas, como o MULTICS e o Intel x86 de 32 bits, combinaram paginação e segmentação:

Cada segmento tem sua própria tabela de páginas.

Isso permite que o espaço de endereçamento seja mais flexível e seguro, mas aumenta a complexidade.

🔸 11. Copy-on-Write (COW)
É uma técnica que evita cópia desnecessária de páginas:

Dois processos podem compartilhar páginas somente leitura.

Se um deles tentar escrever, uma cópia privada é feita (a escrita ocorre na cópia).

É muito usada em fork() e virtualização.

Embora ideal para servidores e desktops, pode não fazer sentido em smartphones, onde o número de processos paralelos e o espaço de armazenamento são limitados.
