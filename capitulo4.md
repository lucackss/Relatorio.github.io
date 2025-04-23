**Capítulo 4 – Sistemas de Arquivos**

**Sistemas de Arquivos**

Um sistema de arquivos é a parte do sistema operacional responsável por gerenciar como os dados são armazenados e acessados em dispositivos de armazenamento, como discos rígidos e SSDs. Ele oferece uma abstração de alto nível para que os usuários interajam com arquivos e diretórios, enquanto internamente lida com detalhes como alocação de blocos, acesso e confiabilidade.

**Estrutura Externa (para o usuário)**

Do ponto de vista do usuário, um sistema de arquivos:

É uma coleção de arquivos e diretórios;

- Permite operações como:
- Leitura e escrita em arquivos;
- Criação e remoção de diretórios;
- Movimentação de arquivos entre diretórios.

Sistemas modernos geralmente utilizam estruturas hierárquicas de diretórios, permitindo a criação de subdiretórios recursivamente, formando uma árvore.

**Estrutura Interna (para o sistema operacional)**

Internamente, o sistema precisa lidar com:

- Alocação de armazenamento;
- Mapeamento de arquivos para blocos de disco;
- Gerenciamento de espaço livre;
- Atributos dos arquivos (como permissões, timestamps, tamanho, etc.).

**Métodos de alocação:**

Alocação contígua: arquivos são armazenados em blocos consecutivos no disco;
- Rápida leitura sequencial;
- Pode causar fragmentação externa.

Alocação encadeada: cada bloco aponta para o próximo (como uma lista encadeada);
- Boa para arquivos sequenciais;
- Ruim para acesso aleatório.

Alocação indexada (i-node): uma estrutura contém os endereços dos blocos do arquivo;
- Excelente para acesso aleatório;
- Amplamente usada em sistemas UNIX.

**Atributos e Metadados**

Arquivos possuem atributos como:

- Nome, tipo, tamanho;
- Data de criação/modificação/acesso;
- Permissões (leitura, escrita, execução);
- Proprietário e grupo.

Esses atributos podem ser armazenados:
- Diretamente nos diretórios;
- Em estruturas separadas, como os i-nodes no UNIX.

**Gerenciamento de Espaço Livre**

Formas comuns de gerenciar o espaço disponível no disco:

- Lista de blocos livres: mantém uma lista dos blocos desocupados.
- Mapa de bits (bitmap): usa um bit por bloco para indicar se está livre (0) ou ocupado (1).

Mapas de bits são mais eficientes para verificar rapidamente grandes áreas de disco, mas podem consumir mais memória.

**Confiabilidade do Sistema de Arquivos**

Falhas de energia, bugs ou corrupção física podem danificar um sistema de arquivos. Para mitigar isso, são utilizados:

- Backups incrementais;
- Programas de verificação e reparo (como fsck no UNIX);
- Sistemas de arquivos com journaling (diário): como o ext4, NTFS, JFS;
- Registram operações pendentes em um log antes de aplicá-las no disco, evitando inconsistências.

**Otimizações de Desempenho**

Cache de blocos: armazena em memória blocos recentemente acessados;

- Leitura antecipada (read-ahead): carrega blocos que provavelmente serão acessados em breve;
- Colocação próxima de arquivos: armazena arquivos relacionados fisicamente próximos para reduzir o tempo de busca;
- Gravações agrupadas (batch writes) para reduzir operações de disco.

**Exemplos de Sistemas de Arquivos**

- ISO 9660: usado em CDs;
- FAT (MS-DOS): simples, mas com limitações em tamanho;
- EXT (UNIX/Linux): baseado em i-nodes, altamente confiável;
- NTFS (Windows): suporte a journaling, compressão, criptografia.

**Estruturas de Diretórios**

Sistemas de arquivos suportam diferentes estruturas de diretórios:

- Plano único (todos os arquivos em um único diretório);
- Hierárquico (árvore de diretórios com caminhos absolutos e relativos);
- Grafos acíclicos (suporte a links rígidos);
- Grafos gerais (links simbólicos).

**Links Rígidos vs. Simbólicos**

Links rígidos (hard links):
- Várias entradas de diretório apontam para o mesmo i-node;
- Compartilham efetivamente o mesmo conteúdo.

Links simbólicos (symlinks):
- São arquivos que contêm o nome de outro arquivo;
- Mais flexíveis, mas quebram se o destino for removido.

**Fragmentação e Compactação**

- A alocação contígua pode causar fragmentação interna (espaço desperdiçado dentro do bloco) e externa (espaço não contíguo no disco).
- Compactação do disco pode ser usada para reorganizar os arquivos e eliminar fragmentações, mas é um processo custoso em termos de tempo.

**Observações Técnicas**

- Um i-node com 10 ponteiros diretos e blocos de 1024 KB pode armazenar diretamente até 10 MB.
- Em sistemas que suportam mapeamento de arquivos para a memória, esse mapeamento deve ser feito com restrições de alinhamento e permissões de acesso.
- A escolha entre alocação contígua, encadeada ou indexada depende de padrões de uso dos arquivos.
