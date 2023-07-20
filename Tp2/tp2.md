# Atributos de código

## Características de um bom projeto de software

Um bom projeto apresenta um conjunto específico de características, e a ausência dessas características é indicativo de um projeto ruim. Segundo Pete Goodliffe, tais características são:

### Simplicidade

Um projeto simples é fácil de entender, coerente e consistente, escrito com o menor código possível, e não menor que isso. O projeto deve cumprir exatamente o que é necessário, usando o mínimo possível, sem quaisquer complexidades desnecessárias.

Sendo a característica mais importante de um código bem projetado, é compreensível que diversos "maus cheiros" de código interfiram na simplicidade do código. De fato, cada um dos maus cheiros descritos por Fowler interferem, em maior ou menor intensidade, com a simplicidade de um projeto. Igualmente, qualquer operação de refatoração, contanto que corretamente aplicada, contribuirá para essa característica.

### Elegância

Essa característica, diretamente associada à simplicidade, diz respeito à estética estrutural do código. Engloba pontos como um adequado controle de fluxo através do sistema, completude entre as partes, resultando em um projeto estruturalmente "belo".

Pode-se estabelecer uma relação direta entre essa caracterísca e o mau cheiro de codigo da "cirurgia com rifle". Esse atributo descreve um código onde uma mudança individual acarreta em pequenas mudanças em diversas classes, o que vai em direta contradição com o que Goodliffe estabelece como característica de elegância, em que "uma única, simples mudança em um lugar não leva a modificações no código em vários outros lugares". Uma oportunidade de refatoração para esse caso específico seria _mover método_ ou _mover campo_ de forma a agrupar as mudanças em uma única classe, ou _incorporar classe_ para agrupar um grupo de comportamentos em uma mesma estrutura.

Quanto ao fluxo do sistema, é possível associar tal característica ao mau cheiro de "aglomerados de dados", que pode ser lidado através da refatoração de _extrair classe_ para transformar aglomerados em objetos, e _introduzir objeto parâmetro_ ou _preservar objeto inteiro_ para simplificar-los.

### Modularidade

Projetos de código são dividos em diversos "módulos", ou "componentes", como classes, objetos, pacotes, dentre outros. Uma boa modularidade atenta-se à coesão e acoplamento do código. Coesão diz respeito a funcionalidades relacionadas entre si serem agrupadas em um mesmo módulo, enquanto acoplamento se refere à interdependência entre módulos diferentes. Um bom projeto deve apresentar forte coesão e baixo acoplamento.

Classe grande, inveja de recursos, homem do meio e classe preguiçosa são apenas alguns exemplos de mau cheiros de código que afetam a modularidade de um projeto. De forma geral, oportunidades de refatoração que interajam intensamente com classes (módulos) e suas interações irão, consequentemente, impactar a coesão e acoplamento do código, melhorando assim a modularidade do projeto. Para os exemplos de mau cheiros citados, podemos aplicar refatorações como _extrair método/mover método_, _mover atributo_ ou _extrair classe_.

### Extensibilidade

Um bom projeto possibilita que novas funções sejam acrescentadas facilmente em espaços apropriados. Um código com boa extensibilidade está preparado para essa expansão, mas sem resultar em um código exacerbadamente genérico, que tenta se preparar para toda e qualquer possibilidade de extensão, mesmo que não faça sentido no contexto do projeto. É necessário um equilíbrio entre o que é essencial agora, o que será necassário no futuro, e o que poderá vir a ser vital mais a frente.

Maus cheiros que podem impactar essa característica de forma mais direta são aquelas ligadas a mudanças ao projeto, como mudanças divergentes, cirurgia com rifle e hierarquias de herança paralelas, que descrevem numerosas mudanças acarretadas por uma singular mudança. Nesses casos, é indicada a refatoração _mover método/mover campo_ ou _incorporar classe/extrair classe_.

Generalidade especulativa é um mau cheiro no caminho oposto, em que o projetista se prepara em excesso para uma funcionalidade que talvez seja implementada no futuro. Manter esse "espaço" para expansão torna-se custoso para o projeto. As operações de refatoração indicadas para esse caso seriam _diminuir hierarquia_, _incorporar classe_ ou _remover parâmetro_, todas formas de "podar" essa generalidade excessiva.

### Ausência de duplicidades

Um bom código não deve se repetir. Dois pedaços de código semelhantes que diferem em poucos detalhes devem ser capazes de serem reescritos na forma de uma única função com parâmetros apropriados. Tal abordagem garante um código simples e elegante, e de manutenção mais eficaz.

Como o próprio nome evidencia, código duplicado é um exemplo de mau cheiro de código que vai contra essa característica de bom projeto. A operação de refatoração indicada é _extrair método_, como dito, para unificar o código duplicado em uma única função.

### Portabilidade

Uma característica que não se aplica a todo projeto, portabilidade diz respeito à independência do código em relação a hardware ou sistema operacional. Como dito, nem todo projeto necessita dessa independência, e gastar recursos nesse viés sem essa necessidade é desvantajoso. Caso seja importante, no entanto, deve ser apropriadamente integrado ao código, pois uma refatoração posterior pode resultar em um código irreparavelmente deselegante, complexo e, em geral, ruim.

Nesse caso, é notável a importância em manter uma boa modularidade, evitando os mais diversos mau cheiros de código desde o início. A tentativa de implementar a portabilidade em um projeto avançado, por exemplo, pode levar a um código impossível de refatorar a um nível que elimine uma quantidade relevante de mau cheiros.

### Idiomático

É importante que um projeto não se atente apenas às boas práticas gerais de projetos, mas também às práticas específicas da linguagem a ser utilizada. É importante saber como ela funciona, para que o código seja facilmente entendido e interpretado pelo programador, e também para que o mesmo possa fazer bom uso. Conhecer os recursos disponíveis, para melhor utilizar-los.

O uso impróprio da linguagem pode levar a diversos mau cheiros de código, a depender do projeto, programador e linguagem. "Obsessão primitiva" por exemplo, visto que estruturas de dados primitivas podem diferir de uma linguagem para outra. Operações de refatoração para esse caso envolvem trocar estruturas, como _trocar dado por objeto_ ou _trocar tipo código por classe_.

### Boa documentação

Como o título sugere, um bom projeto deve ser bem documentado. Isso inclui documentos de arquitetura, comentários, documentação de API e código alto-documentado.

Nisso, destaca=se o mau cheiro de mal uso de comentários, que tende a ocorrer quando o código não apresenta classes e funções com nomes significativos, por exemplo. Em muitos casos, comentários acabam atuando como uma ferramenta para "mascarar" outros mau cheiros de código, sendo necessário portanto a refatoração sobre esses outros problemas. Quanto a comentários, especificamente, recomenda-se as operações de refatoração _extrair método_ e _renomear método_ para reduzir a necessidade de explicação do código.
